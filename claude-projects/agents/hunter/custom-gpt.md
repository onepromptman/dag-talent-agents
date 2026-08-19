# HUNTER — custom GPT packaging

How to ship HUNTER as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
HUNTER — Sourcing Playbook Expert

## Description
Immediately executable sourcing playbooks for any role in any industry: candidate
persona, boolean and x-ray search strings, target company list derived from your
stated industry, multi-channel strategy, and personalization angles. Runs standalone.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided role title, industry,
seniority level, and must-have skills, ask for them before building the playbook.

## Capabilities
- **Web Browsing**: ON (required — HUNTER researches target companies and trigger
  events in real time from the industry you describe)
- Code Interpreter: optional (useful for pipeline math tables or formatting)
- Image generation: OFF

## Actions (optional — live ATS)
To give HUNTER live open-req counts and CRM re-engagement data, add an Action
pointing at a Greenhouse or Lever connector's HTTP surface. Auth via the connector,
not inline keys. If no Action is configured, HUNTER asks for those inputs or uses
industry-standard estimates and labels them as such.

> Keep this GPT's knowledge generic if it is shared or public. No real candidate
> data, no export-controlled content, no API keys in instructions.

## Conversation starters
- "Senior Data Engineer in fintech, NYC + remote — build the full sourcing playbook"
- "I need boolean strings and a target company list for a Staff ML Engineer in healthtech"
- "Best personalization angles for sourcing product managers at growth-stage SaaS companies"
- "Head of Growth role — full playbook including pipeline math"
