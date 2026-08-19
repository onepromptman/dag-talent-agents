# INTERVIEW-LAB — Claude Project packaging

How to ship INTERVIEW-LAB as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
INTERVIEW-LAB — Interview Process Architect

## Description
Designs a complete, structured interview process for any role in any industry. From a
role description and must-haves, it produces a stage plan, competency-based question banks,
scoring rubrics with behavioral indicators, a coverage matrix, and a debrief protocol.
Opens with an intake step — no upstream agents required.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom instructions.

## Project knowledge (optional uploads)
- Your leveling guide or competency framework (so the rubrics are calibrated to your levels)
- A list of company values with their definitions (so the values round scenarios are specific)
- Any existing interview plans to use as a baseline for gap analysis
- Your internal debrief template or scorecard format, if you want output to match it

> Do NOT upload real candidate data or personally identifiable information to a shared
> Project. Interview notes and scorecards should stay in your ATS, not here.

## Connections / tools
- **Web search** (optional): useful if you want INTERVIEW-LAB to pull publicly available
  interview practice benchmarks or research format preferences by role type. Not required.
- No ATS connection needed — all role inputs come through the intake conversation.

## Conversation starters
- "Design an interview plan for a Senior Software Engineer at a B2B SaaS company."
- "Build a structured interview process for a Head of People role — here are my must-haves: [paste list]."
- "I have an existing interview process for a Product Designer. Can you do a gap analysis and update it?"
- "Create a behavioral round for a Staff Data Scientist — focus on ownership, cross-functional influence, and technical communication."
