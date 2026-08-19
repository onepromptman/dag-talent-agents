# Recruit Swarm — n8n Workflow Files

Two importable n8n workflow JSON files ship as the reviewed exemplar for the
recruiting agent swarm. The remaining 7 specialist sub-workflows follow the
same pattern as `sub-oracle.json` and are pending review before release.

## Files

| File | Role |
|---|---|
| `sub-oracle.json` | Oracle specialist sub-workflow (knowledge retrieval) |
| `orchestrator.json` | Orchestrator workflow (classifier + chain router + assembler) |

## Import order

**Sub-workflows must be imported and saved before the orchestrator.**
n8n resolves `executeWorkflow` node targets by workflow ID at import time;
if the target does not exist yet, the node will have an unresolved reference.

1. Import `sub-oracle.json` — save it. Note the workflow ID n8n assigns (visible
   in the URL: `/workflow/<ID>`).
2. Repeat for each additional specialist sub-workflow when those files ship.
3. Import `orchestrator.json` last.
4. In the orchestrator, open each `Call <Specialist>` node and set the
   `workflowId` field to the actual ID of the corresponding sub-workflow
   (replace the `REPLACE_WITH_*_WORKFLOW_ID` placeholders).

## Setting credentials

Every AI Agent node uses an **Anthropic Chat Model** sub-node
(`@n8n/n8n-nodes-langchain.lmChatAnthropic`, typeVersion 1.5).

1. In n8n: **Credentials → New → Anthropic API**.
2. Paste your Anthropic API key.
3. Open each imported workflow, click the Anthropic Chat Model node, and select
   your credential from the dropdown. The placeholder credential ID
   `REPLACE_WITH_YOUR_ANTHROPIC_CRED_ID` will show as unresolved until you do this.

Optional integrations (wire up only if you need them):

- **ATS tool** (Greenhouse/Lever): add an HTTP Request tool node to the Oracle
  AI Agent, pointed at your ATS connector endpoint. Credential lives in n8n's
  credential store — never in the workflow JSON.
- **Vector store / KB tool**: attach a vector store tool node to the Oracle AI
  Agent node for the `benchmark-reference.md` KB. Supported backends: Pinecone,
  Supabase Vector, Qdrant, or n8n's built-in Simple Vector Store.

## Scope of this release

Only the **orchestrator + Oracle** are shipped here as the human-reviewed
exemplar pair. The remaining 7 sub-workflows (Sensei, Atlas, JD-Bot,
Interview-Lab, Hunter, Shakespeare, QA-Bot) follow the identical structural
pattern — `executeWorkflowTrigger` → `lmChatAnthropic` + `outputParserStructured`
attached to an `agent` node → `set` return node — and will ship after their
prompts complete review.

Until those sub-workflows exist, the orchestrator's `Call <Specialist>` nodes
will execute but find no target. You can stub them with simple sub-workflows
that echo their input back as the HANDOFF block for end-to-end flow testing.

## Webhook endpoint

The orchestrator listens at:

```
POST https://<your-n8n-host>/webhook/recruit-swarm-orchestrator
Content-Type: application/json

{
  "request": "Build a full outreach campaign for a senior product designer",
  "org_profile": {
    "company": "Acme Corp",
    "industry": "SaaS / B2B",
    "size_band": "200-500",
    "comp_posture": "STANDARD",
    "locations": "Remote US",
    "work_auth": "",
    "notes": ""
  },
  "role": "Senior Product Designer"
}
```

The workflow responds (via `responseMode: lastNode`) with the assembled
deliverable JSON from the Assemble Deliverable node.
