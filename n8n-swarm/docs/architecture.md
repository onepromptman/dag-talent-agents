# Recruit Swarm (n8n) — Architecture

A generic, importable n8n implementation of an 8-specialist recruiting agent
network with an orchestrator that classifies the request and runs the right slice
of a fixed specialist chain. This is the modernized, brand-agnostic successor to an
earlier Gemini/AgentSpace prompt swarm.

## What changed from the original swarm

| Original (gem3.2, AgentSpace) | This version (n8n, generic) |
|---|---|
| Gemini Agent Designer, paste-in prompts | n8n AI Agent nodes + sub-workflows, importable JSON |
| "Universal Truths" = a private company knowledge base + compliance queries | **org-profile input** the user supplies (company, industry, comp posture, optional work-auth filter) |
| Hardcoded industry competitors, a regulated work-authorization funnel, single-metro benchmarks | all supplied as inputs; nothing brand-specific in the workflow |
| Oracle KB = a private cloud bucket of company-specific reference | Oracle KB = bundled **generic** benchmark reference (public industry reports only) |
| HANDOFF blocks passed as free text by the orchestrator LLM | HANDOFF blocks enforced by **Structured Output Parser** nodes per specialist |
| No live ATS | optional **ATS tool** = the A8 connector (Greenhouse/Lever MCP) |

**Boundary (load-bearing):** public tier = generic only. No real candidate/req data,
no real keys in the workflow JSON. All secrets live in n8n credentials.

## Roster + chain

`Oracle → Sensei → Atlas → JD-Bot → [Interview-Lab] → Hunter → Shakespeare → QA-Bot`

| Specialist | Role | Reads (HANDOFF in) | Writes (HANDOFF out) |
|---|---|---|---|
| Oracle | benchmark retrieval (generic KB) | query from orchestrator | per-agent benchmark schemas |
| Sensei | role comprehension / requirement enrichment | org-profile, role | keywords, synonyms, requirements, pools |
| Atlas | talent market intelligence | Sensei, Oracle | market reality, target companies, messaging |
| JD-Bot | job description | Sensei, Atlas | must/nice skills, titles, disqualifiers |
| Interview-Lab (optional) | interview plan/rubrics | Sensei, JD-Bot | — (terminal asset) |
| Hunter | sourcing playbook | Sensei, Atlas, JD-Bot | persona, value props, personalization |
| Shakespeare | outreach campaign | Atlas, Hunter, Oracle | — (terminal asset) |
| QA-Bot | compliance/consistency validation | all upstream | validation report (always runs last) |

Interview-Lab runs only when interview planning is requested. **QA-Bot always runs
last.** QA-Bot is swarm-only by design (it validates *across* the other agents'
outputs) — it is not shipped as a standalone drop-in agent.

## n8n topology (modern nodes)

```
[Chat/Webhook Trigger]
        │
        ▼
[Orchestrator — AI Agent node]      ← classifies request, picks chain stop-point
        │  (SINGLE_TASK | CAMPAIGN | REVIEW | HYBRID)
        ▼
[Switch — chain scope]              ← deterministic: which specialists to run
        │
        ├─▶ [Oracle subworkflow]      each specialist = Call-n8n-Workflow node
        ├─▶ [Sensei subworkflow]      wrapping its own AI Agent node +
        ├─▶ [Atlas subworkflow]       Structured Output Parser (HANDOFF schema)
        ├─▶ [JD-Bot subworkflow]      + optional ATS tool (A8 connector)
        ├─▶ [Interview-Lab subworkflow]   + optional web-search tool
        ├─▶ [Hunter subworkflow]
        ├─▶ [Shakespeare subworkflow]
        │
        ▼
[QA-Bot subworkflow]               ← always; cross-asset checks on CAMPAIGN
        │
        ▼
[Assemble deliverable]
```

**Why hybrid (orchestrator AI Agent + deterministic chain), not fully agentic:**
the chain order is fixed and well-understood, so a deterministic Switch is cheaper
and more predictable than letting an agent free-pick every hop. The AI Agent earns
its keep on the genuinely fuzzy part — classifying the request and choosing the
stop-point. ("The orchestrator routes logic.")

## HANDOFF passing
Each specialist sub-workflow ends in a **Structured Output Parser** that emits its
HANDOFF block as JSON matching a fixed schema (field names are contracts, same as
gem3.2). The orchestrator passes only the relevant sections forward — never full
outputs. Schemas live in `prompts/<agent>.md` and are mirrored in each sub-workflow.

## ATS connector (optional)
When an ATS connector (Greenhouse / Lever) is available,
Atlas/Hunter/Oracle/QA-Bot get it as an MCP/HTTP **tool** for live reqs, funnel, and
historical data. Until then specialists degrade gracefully and ask the user for the
inputs they'd otherwise pull. Connector credentials live in n8n's credential store.

## Caching (archive check)
Optional. The original swarm cached assets per role with refresh thresholds. In n8n
this maps to a lookup node (e.g. a data table / external store) before the chain;
ship v1 without it and add as an enhancement — note it, don't silently drop it.

## Build order
1. **[this increment]** architecture + generic orchestrator & Oracle prompts (review gate)
2. remaining 7 generic prompts (Sensei, Atlas, JD-Bot, Interview-Lab, Hunter, Shakespeare, QA-Bot)
3. orchestrator workflow JSON + ONE specialist sub-workflow (Oracle) as the n8n exemplar → review
4. remaining specialist sub-workflows
5. README/setup/import docs, manifest, publish dry-run SCAN CLEAN
