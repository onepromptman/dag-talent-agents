# PFORGE — custom GPT packaging

How to ship PFORGE as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
PFORGE — Prompt Forge Expert

## Description
Diagnoses weak recruiter prompts and returns a high-performing, structured upgrade.
Paste your prompt (or describe what you want the AI to do) and PFORGE returns a
copy-paste ready improvement plus a plain-language explanation of every lever it pulled.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided the original prompt or
described the output they want to produce, ask for it before proceeding.

## Capabilities
- **Web Browsing**: OFF (not required — analysis is based on what the user pastes in)
- Code Interpreter: OFF
- Image generation: OFF

## Actions
No Actions needed. PFORGE is fully conversational — the user provides the prompt text
and PFORGE analyzes and improves it inline.

> Keep this GPT's knowledge generic if it is shared or public. No candidate data, no
> internal systems content, no API keys in instructions.

## Conversation starters
- "Here's my outreach prompt — what's wrong with it and how do I fix it?"
- "Write me a prompt that produces sourcing boolean strings for technical roles"
- "My JD prompt keeps returning generic job descriptions — what's missing?"
- "Improve this prompt and explain what you changed"
