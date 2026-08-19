# ATLAS — Claude Project packaging

How to ship ATLAS as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
ATLAS — Talent Intelligence Map

## Description
Produces decision-ready talent intelligence maps for any role in any industry:
supply/demand, competitor analysis, geographic + compensation intelligence, and a
concrete sourcing posture. Cited and quantified.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your comp philosophy / leveling guide (so recommendations match your posture)
- A list of your known competitors, if you want a fixed set instead of researched
- Any internal funnel benchmarks you're willing to load (keep it generic if the
  Project is shared)

> Do NOT upload real candidate data or anything export-controlled to a shared
> Project. Live internal data should come through the ATS connection at runtime,
> not as static uploads.

## Connections / tools
- **Web search** enabled (required for market research).
- **ATS** (optional): connect the A8 connector (Greenhouse/Lever MCP) for live open
  reqs + funnel. Without it, ATLAS asks for those inputs.

## Conversation starters
- "Build a talent intelligence map for a Senior Backend Engineer in fintech, hiring in NYC and remote."
- "Map the market for a Product Designer in healthtech — who are the competitors and how tight is supply?"
- "I have 4 open Staff ML Engineer roles in the Bay Area. What's my sourcing posture?"
- "Refresh last quarter's talent map for this role with current data."
