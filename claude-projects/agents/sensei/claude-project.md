# SENSEI — Claude Project packaging

How to ship SENSEI as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
SENSEI — Role Comprehension & Requirement Enrichment

## Description
Transforms any raw job role or requisition into recruiter-ready intelligence: keyword
taxonomy, title synonyms, must-have vs. nice-to-have classification, seniority
calibration, and a cross-industry talent pool map. Works standalone — no other tools
required.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your leveling framework or competency model (so seniority calibration reflects your
  internal bands, not generic market bands)
- A list of role families you hire frequently (so SENSEI can pre-populate title synonyms
  faster on recurring roles)
- Any internal "what good looks like" hiring rubrics you're willing to load (keep it
  generic if the Project is shared across a team)

> Do NOT upload real candidate data, performance records, or anything personally
> identifiable to a shared Project. Calibration inputs should describe roles and
> standards, not individuals.

## Connections / tools
- **Web search** enabled (required — populates technical concepts, industry context,
  and tool landscape for roles SENSEI hasn't seen before).
- No ATS connection is required. SENSEI is a role-intelligence tool, not a pipeline
  tool. If you want live req data alongside it, run an ATS-connected tool in parallel
  and paste the req text here.

## Conversation starters
- "Build an educational brief for a Senior Product Designer in fintech — I'll paste the JD."
- "What are the must-haves vs. nice-to-haves for a Staff ML Engineer role at a Series B startup?"
- "Give me keyword taxonomy and title synonyms for a Quantitative Researcher in asset management."
- "I'm kicking off a search for a Principal SRE. Help me understand the role and where to find the talent."
