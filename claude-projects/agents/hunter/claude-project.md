# HUNTER — Claude Project packaging

How to ship HUNTER as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
HUNTER — Sourcing Playbook Expert

## Description
Builds an immediately executable sourcing playbook for any role in any industry:
candidate persona, boolean and x-ray search strings, prioritized target company list
derived from the stated industry, multi-channel strategy, and personalization angles.
No upstream agents required.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your leveling guide or title taxonomy (so HUNTER's title synonyms match your
  internal naming conventions)
- A list of your known competitors, if you want a fixed set instead of researched
- Any historical sourcing data — which strings generated responses, which channels
  converted — to calibrate pipeline math and channel priority
- Your comp philosophy (so personalization angles reference the right value props)

> Do NOT upload real candidate data or anything export-controlled to a shared
> Project. Live ATS data should come through a connector at runtime, not as
> static uploads.

## Connections / tools
- **Web search** enabled (required — HUNTER researches target companies and trigger
  events in real time from the stated industry).
- **ATS** (optional): connect a Greenhouse or Lever connector for live open-req
  counts and any CRM re-engagement data. Without it, HUNTER asks for those inputs
  or uses industry-standard estimates.

## Conversation starters
- "Build a sourcing playbook for a Senior Data Engineer in fintech, hiring in NYC and remote."
- "I need to source Staff Software Engineers in healthtech — help me build a target list and search strings."
- "What are the best personalization angles for sourcing product managers at Series B SaaS companies?"
- "Build a playbook for a Head of Growth role — I need the full boolean set and company list."
