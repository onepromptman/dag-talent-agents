# JD-BOT — Claude Project packaging

How to ship JD-BOT as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
JD-BOT — Job Description Architect

## Description
Produces sharp, inclusive, conversion-oriented job descriptions for any role in any
industry: market-calibrated requirements, must-have vs. nice-to-have skills, leveled
titles, disqualifiers, and bias-checked language. Standalone — no upstream agents
required.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your company's standard boilerplate (About section, EEO statement, comp bands) so
  JD-BOT can insert real text instead of placeholders
- Your leveling guide or job family matrix (so seniority calibration matches your
  internal ladder)
- A list of role-specific forbidden phrases or terminology standards for your org

> Do NOT upload real candidate data, internal compensation data with individual names,
> or anything regulated to a shared Project. Org-level comp bands are fine; individual
> offer details are not.

## Connections / tools
- **Web search**: optional (useful if JD-BOT needs to research standard role terminology
  or benchmark requirements for an unfamiliar role)
- **ATS**: optional — if you connect a Greenhouse or Lever integration, JD-BOT can pull
  existing JD versions and propose an update vs. create-new decision. Without it,
  JD-BOT works entirely from what you provide in the conversation.

## Conversation starters
- "Write a JD for a Senior Data Engineer, fintech industry, NYC hybrid, TIGHT market."
- "Build a job description for a Head of People, Series B startup, fully remote."
- "I have a Staff Product Manager role in healthtech — help me calibrate requirements for a tight market."
- "Update this existing JD based on a MODERATE market classification: [paste JD]"
