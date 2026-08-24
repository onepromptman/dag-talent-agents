# Recruit Swarm (n8n)

A generic, importable **8-specialist recruiting agent network** for n8n. An
orchestrator interprets your request, calls the right specialists, and assembles
the deliverable — job descriptions, talent maps, sourcing playbooks, outreach
campaigns, interview plans, or a scoped multi-asset package.

This is the brand-agnostic successor to an earlier Gemini/AgentSpace prompt swarm.
It is generic by construction: **bring your own company context (an org profile),
your own LLM key, and optionally your own ATS connection.** No real candidate or
requisition data ships in this repo.

## v2 — Agents-as-Tools (current)

The current build is **one workflow** where the orchestrator is an AI Agent and
each specialist is attached as an **AI Agent Tool** sub-node
(`@n8n/n8n-nodes-langchain.agentTool`) — agents calling agents. The orchestrator
decides which specialists a request needs, calls them as tools, and emails the
result. This replaces the v1 sub-workflow design: **no `executeWorkflow` nodes, no
workflow-ID wiring, no multi-file import order.**

→ Import **[`workflows/v2-agents-as-tools/recruit-swarm-v2.json`](workflows/v2-agents-as-tools/recruit-swarm-v2.json)**
and follow [`workflows/README.md`](workflows/README.md).

Dynamic routing per request type: a role brief calls Oracle/Sensei/QA-Bot; a JD
adds JD-Bot; a talent map adds Atlas; and so on. The orchestrator emails the
assembled result. Structurally complete and import-tested; run it end to end with
your own Anthropic + Gmail credentials (see Quickstart). The legacy v1 design is
preserved under [`workflows/legacy-v1/`](workflows/legacy-v1/).

## The specialists

`Oracle → Sensei → Atlas → JD-Bot → [Interview-Lab] → Hunter → Shakespeare → QA-Bot`

| Specialist | Produces |
|---|---|
| **Oracle** | recruiting benchmark data (from a generic reference) |
| **Sensei** | role comprehension + requirement enrichment |
| **Atlas** | talent market intelligence + competitive analysis |
| **JD-Bot** | the job description (source of truth for requirements) |
| **Interview-Lab** | structured interview plan + rubrics (optional) |
| **Hunter** | sourcing playbook with copy-paste search strings |
| **Shakespeare** | multi-channel outreach campaign |
| **QA-Bot** | compliance + cross-asset consistency check (always runs last) |

In v2 these are tools the orchestrator calls by name — it runs only the ones a
request needs, in the order it decides.

## Quickstart (~3 min)

1. Import `workflows/v2-agents-as-tools/recruit-swarm-v2.json`.
2. Create two credentials in n8n and select them on the nodes (the JSON ships with
   placeholder IDs, never real keys):
   - **Anthropic API** → every *Anthropic Chat Model* node (model is `claude-sonnet-4-6`
     in ID mode; change to any Claude model your key supports).
   - **Gmail OAuth2** → the *Email Deliverable* node; set the recipient address.
3. Activate, then POST to the webhook, e.g.
   `{"request": "Just a sourcing strategy for a Product Designer at a 600-person SaaS"}`.
   The webhook returns immediately; the deliverable arrives by email.

## What's NOT included
- No real candidate/requisition data, no company-specific context, no API keys.
- The ATS connector is optional and not bundled here. Without it, specialists ask
  you for the inputs they'd otherwise pull live.
- A live benchmark data source for Oracle (n8n Data Table or vector-store RAG) is
  an architected enhancement, not yet wired.

## How it works
See [`docs/architecture-v2.md`](docs/architecture-v2.md) for the v2 topology (AI
Agent + agentTool specialists), the n8n node choices, and the Cloud constraints
(async webhook response, agent timeout, scoping). The original v1 topology is in
[`docs/architecture.md`](docs/architecture.md).

## Status
**v2** (agents-as-tools) — structurally complete and import-tested; wire your own
Anthropic + Gmail credentials for a live end-to-end run. v1 (sub-workflow design)
retained under `workflows/legacy-v1/` for reference.
