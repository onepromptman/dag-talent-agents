---
agent: Outreach Campaign Architect
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# Outreach Campaign Architect (SHAKESPEARE) — Context Guide

## What it does

SHAKESPEARE writes candidate outreach campaigns from scratch: it takes a role, a target persona, and a few facts about your company and returns ready-to-send connection notes, emails, and InMail copy — personalized by seniority level, employer type, and candidate motivation. Nothing needs to be formatted before you paste it in.

## What you get back

- **Connection Note** — 300-character opener for LinkedIn (fits the character cap, ready to copy)
- **Single Message** — a full email (~150 words, 4 paragraphs) or InMail (~700 characters, 3 paragraphs), with two subject line variants (A/B) and a suggested follow-up line
- **5-Touch Email Sequence** — five timed emails (Day 0 through Day 21) plus a mid-sequence LinkedIn note — only produced when you ask for it
- **Personalization tokens** — placeholder labels like `[[FirstName]]` or `[[RecentProject]]` that mark exactly where you fill in candidate-specific detail
- **Confidence block** — a short note at the end declaring what the agent used from your inputs and what it assumed, so you know what to verify

Typical format: structured sections with clear labels, character/word counts on every piece of copy, and A/B subject line pairs. Prose only in message bodies — no bullets or headers that would look odd inside an email.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | Required | None — enable in Claude Project settings | Cannot research a specific candidate's recent work or news; personalization relies entirely on what you provide |
| Messaging guidelines doc | Optional | Upload a PDF or doc to the Claude Project knowledge base | Agent asks you for proof points and tone guidance each session |
| Target-employer pain-point map | Optional | Upload to the Claude Project knowledge base | Agent uses general employer-type logic instead of your curated angles |
| Historical reply-rate data | Optional | Upload to the Claude Project knowledge base | Agent uses industry averages as benchmarks instead of your actual numbers |

No ATS connection is needed. SHAKESPEARE works from what you type — it does not pull candidate records from your pipeline.

## What to give it before you start

### Required

| Input | What it means | Example |
|---|---|---|
| Role title | The exact job title you are hiring for | "Senior Data Engineer" |
| Industry or sector | The space your company operates in — shapes which competitors and pain points are relevant | "Fintech" or "Climate tech / energy storage" |
| Company context | Your company name or description, rough size, what you do, and one or two verifiable facts a candidate could look up | "Series B startup, 120 people, building supply-chain software — shipped to 40 enterprise customers this year, team includes engineers from two well-known logistics companies" |
| Target persona | Seniority level, likely current employer type(s), and the main reason someone in this role would consider moving | "Senior-level, currently at a late-stage startup or big tech company, motivated by technical ownership and wanting to see their work ship faster" |

### Optional (each unlocks better output)

| Input | What it means | Example |
|---|---|---|
| Channels to produce | Which formats you want — Connection Note only, Single Message only, or the full 5-Touch Sequence (say so explicitly) | "Connection Note and email" or "I need the full 5-touch sequence" |
| Personalization tier | How much research effort the copy assumes: High-Touch (named candidate, specific project), Standard (employer-level hook), or Basic (name and company only) | "High-Touch — this is a priority hire" |
| Specific candidate details | Name, current employer, a recent project or career signal, and preferred channel — optional, but switches the agent into full personalization mode and produces copy for that person only | "Jordan, currently a Staff Engineer at a mid-size SaaS company, recently open-sourced a data pipeline library, prefers LinkedIn" |
| Market context | Whether qualified candidates are rare and heavily recruited (Drought) or plentiful (Flood) — changes urgency and tone | "Drought — this is a specialized hardware role with limited supply" |

## How to format your inputs

- **Paste free text.** You do not need a form or a template — a few sentences describing the role and persona is enough. SHAKESPEARE will ask follow-up questions if something critical is missing.
- **Give facts, not adjectives.** "We shipped to 40 customers this year" is usable. "We're a world-class team with an exciting product" is not — the agent will not use unverifiable claims.
- **Name the candidate only when you want personalized copy.** If you are building pipeline templates, leave the candidate blank; the agent defaults to template mode and produces `[[tokens]]` instead.
- **Ask for the 5-touch sequence explicitly.** The agent never generates it unless you ask — a Single Message is the default.
- **Do not paste full LinkedIn profiles or resumes.** Pull out the two or three details that are actually relevant (recent project, employer, seniority signal) and paste those instead.

## When to refresh

Re-run SHAKESPEARE (or update the output) when:

- The role scope changes significantly — different level, different team, or different technical focus
- Your company proof points change (new funding round, product milestone, headcount shift)
- Reply rates drop below your baseline for more than two weeks — the hook angle may be stale
- You have moved a candidate to a re-engagement situation (they were contacted before) — the copy needs a different opening that acknowledges prior contact
- The talent market shifts noticeably (Drought market becomes Flood or vice versa)

Output shelf life: campaign templates are typically good for one hiring quarter or until a major company or market change, whichever comes first. Candidate-specific copy is one-time use.

## Start here

Copy either of these openers into SHAKESPEARE and press send:

**Option 1 — Pipeline templates (most common):**

> Build outreach templates for a Senior Data Engineer pipeline. Candidates are mostly coming from late-stage startups or big tech. Primary motivation is technical ownership — they want their work to actually ship. Our company is a Series B fintech startup, about 150 people, building real-time payment infrastructure. Verifiable proof points: processed over 10 billion transactions last year, team includes engineers from two major payment networks. I need a Connection Note and a Single Email. Standard personalization tier.

**Option 2 — Specific candidate (personalized copy):**

> Write a personalized LinkedIn InMail and Connection Note for a candidate named Alex. They are currently a Staff ML Engineer at a well-known enterprise software company, recently published a paper on large-scale model distillation, and I found them through a referral. The role is Principal ML Engineer at our company — we are a Series A climate tech startup, 80 people, building grid-optimization software. Proof point: our models run on 12 regional grids covering 4 million households. High-Touch tier.
