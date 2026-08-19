---
agent: Prompt Forge Expert
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# Prompt Forge Expert (PFORGE) — Context Guide

## What it does

PFORGE takes any recruiter prompt — whether it is a rough idea or something you have been using for months — and rebuilds it into a clean, structured version that produces better AI output. It also explains every change it made in plain English so you can write stronger prompts yourself next time.

## What you get back

- A diagnostic score showing exactly where your original prompt was weak, partial, or strong across six dimensions
- A fully upgraded, copy-paste-ready prompt structured with a role, inputs, method, output format, quality gates, and style guide
- A "Why I changed what I changed" section — one plain-language sentence per fix, no jargon
- (When relevant) a note on how to adapt the improved prompt for a related use case (e.g., a follow-up message variant if you submitted an outreach prompt)

Typical format: a short score table, then the full upgraded prompt in a code block, then a brief explanation list.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Your chat window (Claude Project or custom GPT) | Yes | Just open and paste | Nothing works without this |
| Web search | No | None | PFORGE works entirely from the text you paste in — it does not browse the internet |
| ATS or HRIS connection | No | None | Not needed — no data is pulled from external systems |
| File uploads (style guide, JD template, etc.) | No | Upload to Project knowledge once | PFORGE will still work; it just cannot match your house style without these |

## What to give it before you start

**Required**

| Input | What it means | Example |
|---|---|---|
| The prompt or request you want improved | Paste your current prompt verbatim, or describe what you want the AI to do if you do not have a prompt yet | "Write a cold outreach message for a senior software engineer role" |
| Output type (if not obvious from the prompt) | What should the AI produce? | Job description, boolean search string, outreach message, screening questions, offer letter, intake notes, scorecard |

**Optional — each one unlocks a better result**

| Input | What it means | Example |
|---|---|---|
| Target AI tool | Which AI will run this improved prompt | Claude, ChatGPT, Gemini — defaults to any AI if you skip this |
| Audience for the AI's output | Who reads what the AI produces | Candidate, hiring manager, recruiter, executive |
| Known constraints | Any rules the output must follow | Under 150 words, must include salary range, must use these section headers |

## How to format your inputs

- Paste your prompt exactly as you have been using it, even if it is one rough sentence — PFORGE is designed to work with messy starting points.
- If you do not have a prompt yet, describe the task in plain English: "I want AI to help me write screening questions for a sales role."
- Do not clean up your prompt before submitting. The rough version is what PFORGE diagnoses.
- Include constraints as a separate note at the end, not woven into the prompt text: "Constraint: must stay under 120 words."
- Do not upload candidate names, resumes, or any personal data — PFORGE only needs the prompt template itself, not live data.

## When to refresh

Re-run PFORGE when:
- The AI tool you use releases a major update and your prompt starts producing worse results
- Your target output type changes (e.g., you move from LinkedIn InMail to email outreach)
- Your team's style guide or required sections change
- You get feedback that AI output is too generic, too long, or hitting the wrong tone

Output shelf life: improved prompts are stable for months. They do not expire on a schedule — re-run only when the underlying AI tool or your requirements change.

## Start here

Copy either opener below and paste it directly into PFORGE:

> "Here's the prompt I've been using for outreach messages — tell me what's weak about it and give me a better version: [paste your prompt here]"

> "I don't have a prompt yet. I want an AI to write sourcing boolean strings for technical roles. Give me a prompt that will actually work."
