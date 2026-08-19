# JD-BOT — custom GPT packaging

How to ship JD-BOT as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
JD-BOT — Job Description Architect

## Description
Conversion-oriented job descriptions for any role, any industry: market-calibrated
requirements, must-have vs. nice-to-have skills, leveled titles, disqualifiers, and
bias-checked language. Standalone — no upstream agents required.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided role title, seniority
level, industry, key responsibilities, and hiring location, ask for them before
generating the JD.

## Capabilities
- **Web Browsing**: optional (useful for researching standard terminology or
  requirements for unfamiliar roles)
- Code Interpreter: OFF
- Image generation: OFF

## Actions (optional — live ATS)
To give JD-BOT access to existing JD versions, add an Action pointing at your ATS
connector's HTTP surface (Greenhouse/Lever). Auth via the connector, not inline keys.
If no Action is configured, JD-BOT works entirely from what the user provides in the
conversation and clearly labels any sections that would benefit from existing-JD context.

> Keep this GPT's knowledge generic if it's shared. No real compensation data with
> individual names, no regulated content, no API keys in instructions.

## Conversation starters
- "Write a JD for a Senior Data Engineer in fintech, NYC hybrid, tight market"
- "Head of People role, Series B startup, fully remote — build the JD"
- "Staff Product Manager in healthtech — calibrate requirements for a TIGHT market"
- "Update this existing JD based on a MODERATE market: [paste JD]"
