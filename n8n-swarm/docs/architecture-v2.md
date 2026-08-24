# Recruit Swarm v2 — Architecture (Agents-as-Tools)

v2 replaces the v1 sub-workflow design (orchestrator + `executeWorkflow` calls to
separate specialist workflows) with the modern n8n AI-Agent pattern: **one
workflow, specialists attached as tools.**

## Topology

```
Webhook (POST, responseMode: onReceived)
   │
   ▼
Orchestrator  ── AI Agent (@n8n/n8n-nodes-langchain.agent, Tools Agent)
   ├─ ai_languageModel ── Anthropic Chat Model (lmChatAnthropic, claude-sonnet-4-6)
   └─ ai_tool ─┬─ Oracle          ┐
               ├─ Sensei          │  each is an AI Agent Tool
               ├─ Atlas           │  (@n8n/n8n-nodes-langchain.agentTool),
               ├─ JD-Bot          │  with its OWN Anthropic Chat Model and
               ├─ Interview-Lab   │  its system prompt from prompts/<name>.md
               ├─ Hunter          │
               ├─ Shakespeare     │
               └─ QA-Bot          ┘
   │
   ▼
Email Deliverable ── Gmail (sends the orchestrator's final output)
```

## Why agents-as-tools

- **No sub-workflow wiring.** v1 needed each specialist as a separate workflow,
  imported in order, with `REPLACE_WITH_*_WORKFLOW_ID` placeholders hand-set in the
  orchestrator's `executeWorkflow` nodes. v2 has none of that — the specialists are
  sub-nodes in the same workflow.
- **Dynamic routing.** The orchestrator (Tools Agent) reads the request and calls
  only the specialist tools it needs, in the order it reasons about — e.g. a role
  brief → Oracle, Sensei, QA-Bot; a JD → + JD-Bot; a talent map → + Atlas.
- **Agents calling agents.** Each `agentTool` is a full agent (own model + prompt),
  so a specialist reasons independently and returns a result the orchestrator
  composes — the "conversational handoff" pattern, without a rigid HANDOFF schema.
- Specialists return free text (no forced structured-output parser), which avoids
  the brittle "model output doesn't fit required format" failure mode.

## n8n Cloud constraints (and how v2 handles them)

1. **Gateway ~100s response cap.** Hosted n8n sits behind a CDN that times out a
   single synchronous HTTP response at ~100s. A multi-specialist run exceeds that.
   → The webhook uses **`responseMode: onReceived`**: it returns 200 immediately and
   the workflow runs async. **The deliverable is the email, not the HTTP body.**
2. **AI-Agent ~5-min execution timeout.** Each specialist hop is ~30s, so a *full
   8-specialist campaign* in one request can approach the limit. → The orchestrator
   is prompted to **scope** the chain; scoped requests (2–4 specialists) are the
   recommended sweet spot. Split a full campaign into a couple of requests.
3. **`maxIterations`.** The orchestrator's tool-call loop is set to **25** so complex
   multi-tool requests don't hit the iteration cap.
4. **No `$env` on Cloud.** All secrets are credentials, never env vars or inline keys.

## Extending

- **Live data for Oracle.** Attach a tool to the Oracle agent: an n8n **Data Table**
  (`n8n-nodes-base.datatable`) of benchmarks via a Call-n8n-Workflow tool, or a
  **vector-store RAG** tool (`toolVectorStore` + an in-memory/Qdrant/PGVector store)
  over a benchmark reference. Embeddings need a non-Anthropic provider (Anthropic
  ships no embeddings API) — e.g. OpenAI `text-embedding-3`.
- **Conversational memory.** Add a Window Buffer Memory keyed by `sessionId` for
  multi-turn use.
- **Other channels.** Swap the Gmail node for Slack / a response node as needed.

## Credentials

The shipped JSON contains **placeholder** credential IDs only
(`REPLACE_WITH_YOUR_ANTHROPIC_CRED_ID`, `REPLACE_WITH_YOUR_GMAIL_CRED_ID`) and a
placeholder recipient (`you@example.com`). Wire your own Anthropic + Gmail
credentials after import. No keys are ever stored in the workflow JSON.
