# ATLAS — custom GPT packaging

How to ship ATLAS as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
ATLAS — Talent Intelligence Map

## Description
Decision-ready talent intelligence for any role, any industry: supply/demand,
competitor analysis, geographic + compensation intelligence, sourcing posture.
Cited and quantified.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided role, industry, and
location, ask for them before researching.

## Capabilities
- **Web Browsing**: ON (required for market research)
- Code Interpreter: optional (useful for funnel math / charts)
- Image generation: OFF

## Actions (optional — live ATS)
To give ATLAS live open-req and funnel data, add an Action pointing at the A8 ATS
connector's HTTP surface (Greenhouse/Lever). Auth via the connector, not inline
keys. If no Action is configured, ATLAS asks the user for current open-role counts
and any internal benchmarks.

> Keep this GPT's knowledge generic if it's shared/public. No real candidate data,
> no export-controlled content, no API keys in instructions.

## Conversation starters
- "Talent map for a Senior Backend Engineer in fintech, NYC + remote"
- "How tight is the market for a Product Designer in healthtech?"
- "4 open Staff ML Engineer roles, Bay Area — what's my sourcing posture?"
- "Refresh an existing talent map with current data"
