# SHAKESPEARE — custom GPT packaging

How to ship SHAKESPEARE as a custom GPT. The system prompt lives in `agent.md`
(the source of truth); this file is just the platform wrapper.

## Name
SHAKESPEARE — Outreach Campaign Architect

## Description
Designs multi-touch candidate outreach campaigns for any role in any industry:
sequence cadence, channel mix, personalized copy, and value-prop framing.
Standalone. No upstream agents required.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided role, company
context, and target persona, ask for them before producing any copy.

## Capabilities
- **Web Browsing**: ON (recommended for personalization research — candidate
  publications, employer news, recent projects)
- Code Interpreter: OFF (not needed)
- Image generation: OFF

## Actions (optional)
No live data connections are required for SHAKESPEARE to function. If you want to
pre-load approved proof points or employer pain-point maps, upload them as
knowledge files rather than wiring an Action.

> Keep this GPT's knowledge generic if it's shared or public. No real candidate
> data, no API keys in instructions, no export-controlled content.

## Conversation starters
- "Outreach templates for a Senior Data Engineer pipeline — big tech candidates, ownership-motivated"
- "Personalized InMail for someone who just shipped a major open-source project"
- "5-touch sequence for a Principal ML Engineer — drought market, highly recruited"
- "Critique this connection note — hook isn't landing"
