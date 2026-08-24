# Recruit Swarm — n8n Workflow Files

## v2 (current) — `v2-agents-as-tools/recruit-swarm-v2.json`

A **single importable workflow**. The orchestrator is an AI Agent and every
specialist (Oracle, Sensei, Atlas, JD-Bot, Interview-Lab, Hunter, Shakespeare,
QA-Bot) is attached to it as an **AI Agent Tool** sub-node
(`@n8n/n8n-nodes-langchain.agentTool`). The orchestrator decides which specialists
a request needs, calls them as tools (agents calling agents), and emails the
assembled deliverable.

This replaces the v1 sub-workflow pattern — **no `executeWorkflow` nodes, no
workflow-ID wiring, no separate sub-workflow files to import in order.**

### Import (one file, ~3 min)
1. Import `v2-agents-as-tools/recruit-swarm-v2.json`.
2. Create two credentials in n8n and select them on the nodes (the JSON ships with
   placeholder credential IDs, never real keys):
   - **Anthropic API** → on every *Anthropic Chat Model* node
     (placeholder `REPLACE_WITH_YOUR_ANTHROPIC_CRED_ID`). The model is set in ID
     mode to `claude-sonnet-4-6`; change it to any Claude model your key supports.
   - **Gmail OAuth2** → on the *Email Deliverable* node
     (placeholder `REPLACE_WITH_YOUR_GMAIL_CRED_ID`); set the recipient
     (`you@example.com`) to your address.
3. Activate. POST to the webhook with `{"request": "..."}` (e.g. *"Just a role
   brief for a Senior Backend Engineer at a 300-person fintech"*). The webhook
   returns immediately (`onReceived`); the deliverable arrives by email.

### Notes / limits
- **Scope your request.** Each specialist hop is ~30s. Scoped asks (2–4
  specialists: a brief, a JD, a talent map, a sourcing strategy) run comfortably.
  A single *full 8-specialist campaign* can approach n8n's ~5-min AI-Agent
  timeout — split it into a couple of requests if needed.
- The webhook uses `responseMode: onReceived` on purpose: long agent runs would
  otherwise hit the hosting gateway's ~100s response cap. Output is the email.
- Oracle currently reasons from the model's knowledge. To wire live benchmark
  data, attach an n8n **Data Table** or a **vector-store RAG** tool to the Oracle
  node (embeddings need a non-Anthropic provider — Anthropic ships none).

## v1 (legacy) — `legacy-v1/`

The original sub-workflow design (`orchestrator.json` + `sub-oracle.json`),
kept for reference. It dispatched specialists as separate `executeWorkflow`
sub-workflows wired by workflow ID — superseded by v2. See
[`legacy-v1/README.md`](legacy-v1/README.md) for its (more involved) import order.
