# PFORGE — Claude Project packaging

How to ship PFORGE as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
PFORGE — Prompt Forge Expert

## Description
Turns a vague recruiter request or a weak existing prompt into a high-performing,
structured version. Diagnoses what is wrong, applies six proven structural levers, and
returns the improved prompt plus a plain-language explanation of every change — so you
write better prompts next time.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your house style guide or tone standards (so the improved prompts match your org's voice)
- A list of your org's required sections for job descriptions or offer letters
- Any internal prompt library you want PFORGE to reference when generating examples

> Do NOT upload candidate data, real employee records, or anything export-controlled to a
> shared Project. PFORGE works entirely from what you paste into the conversation.

## Connections / tools
- **Web search**: not required — PFORGE works from the prompt you paste in.
- No ATS connection needed. All analysis is based on the text you provide.

## Conversation starters
- "Here's the prompt I've been using for outreach messages — what's weak about it and how do I fix it?"
- "I want an AI to write me sourcing boolean strings. Give me a prompt that will actually work."
- "Turn this job description prompt into something that produces JDs worth reading."
- "I described what I want and the AI gave me something generic. Here's what I sent — what's missing?"
