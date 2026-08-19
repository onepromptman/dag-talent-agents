---
agent: Job Description Architect
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# Job Description Architect (JD-BOT) — Context Guide

## What it does

JD-BOT turns the notes you already have about a role into a complete, market-calibrated job description ready to post. It also flags biased language and documents every requirement adjustment it makes, so your JD is defensible and consistent before it ever goes live.

## What you get back

- **About [Company]** — a 3-4 sentence company intro (uses your boilerplate if you give it one; leaves a clear placeholder if not)
- **The Role** — 3-4 sentences written from the candidate's perspective explaining what they'll own and why it matters
- **What You'll Do** — 5-7 specific, action-verb bullets covering scope, collaboration, and ownership
- **What You Bring: Required** — 5-7 market-calibrated, screenable requirements (plus a work-authorization bullet if you provide one)
- **What You Bring: Nice to Have** — 3-4 genuinely additive differentiators
- **What We Offer** — comp range, benefits, location/remote policy, and growth framing (never "competitive salary")
- **Market Calibration Log** — a table showing every requirement that was adjusted and why
- **Inclusive Language Audit** — a table flagging and resolving any biased or exclusionary phrases

Typical format: a single structured document, 500-900 words of JD body, plus the two audit tables at the end.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | No | Enable in Project settings if desired | JD-BOT works entirely from what you provide; web search only helps it research niche role terminology it hasn't seen before |
| ATS connection (e.g. Greenhouse, Lever) | No | Requires an integration if your platform supports it | JD-BOT writes from scratch based on your inputs — no ATS access needed |

## What to give it before you start

### Required — JD-BOT will ask for these if you skip them

| Input | What it means | Example |
|---|---|---|
| Role title | The job title you want to post | "Senior Product Manager" |
| Seniority / level | Whether this is IC or manager; junior / mid / senior / staff / principal | "Senior IC, no direct reports" |
| Industry or sector | The field this role sits in — shapes terminology and comp framing | "Fintech" or "Healthcare SaaS" |
| Key responsibilities | What the person will own and do day-to-day | "Own the data pipeline roadmap, partner with engineering on quarterly planning, lead vendor evaluations" |
| Must-have requirements | The non-negotiables a candidate must have on day one | "5+ years in data engineering, proficiency in SQL and Python, experience with cloud data warehouses" |
| Hiring location(s) and remote policy | Where the role is based and whether remote is allowed | "New York, NY — hybrid 3 days/week" or "Fully remote, US only" |

### Optional — skip any of these, but each one unlocks a better output

| Input | What it means | Example | Unlocks |
|---|---|---|---|
| Nice-to-have skills | Skills that would make a candidate exceptional but aren't blockers | "Experience with dbt, exposure to real-time streaming" | Prevents JD-BOT from guessing; ensures your differentiators match the role |
| Company context | Name, size, mission, comp posture (pay above / at / below market) | "Series C startup, 200 employees, mission: democratize financial data, pay at market" | Replaces the generic company placeholder with real copy |
| Market classification | How competitive is this talent market? Paste from ATLAS if you use it, or give your gut read | "TIGHT" or "Very hard to hire right now" | Triggers automatic requirement adjustments calibrated to supply/demand — without this, JD-BOT assumes a moderate market |
| Work-authorization constraint | Only include if your org has a stated policy; JD-BOT never assumes one | "Must be authorized to work in the US without sponsorship" | Adds a compliant funnel filter as the final Required bullet using only your language |
| Your standard boilerplate | Paste your About section, EEO statement, or comp band language | Your standard EEO paragraph | Replaces every placeholder with real, approved text so the output is post-ready |

## How to format your inputs

- **Paste free text — no special formatting needed.** Bullet points, a paragraph, or even rough notes all work. JD-BOT will organize them.
- **Do include numbers when you have them.** "5+ years" is better than "experienced." "Team of 12 engineers" is better than "large team."
- **Do name the tools and systems that matter.** "Snowflake and dbt" tells JD-BOT more than "data tools."
- **Don't over-polish before pasting.** Raw hiring manager notes are fine — that's exactly what JD-BOT is built to turn into polished copy.
- **Don't paste a previous JD and assume it counts as input.** If you want JD-BOT to update an existing JD, say "update this JD" and paste it — it will treat that as context and ask which inputs have changed.

## When to refresh

Re-run JD-BOT when any of the following happen:

- The hiring manager changes the role scope or reporting structure
- More than 60 days pass without a hire and you're revisiting requirements
- Your market classification changes (e.g., talent supply tightens or loosens)
- Your compensation bands are updated and the posted range is now out of date
- You receive legal or HR feedback that requires language changes
- A new location or remote policy is added to the role

Output shelf life: 60 days in a stable market; 30 days or less if hiring conditions are shifting.

## Start here

Copy either opener below and paste it directly into the JD-BOT conversation:

**Option 1 — you have the details ready:**
```
Write a job description for a Senior Data Engineer. Industry: fintech. Location: New York, NY — hybrid 3 days/week. Seniority: senior IC. Key responsibilities: own the data pipeline roadmap, partner with engineering on quarterly planning, lead vendor evaluations. Must-haves: 5+ years in data engineering, strong SQL and Python, experience with cloud data warehouses (Snowflake preferred). Market: TIGHT. Pay: upper half of band, no equity.
```

**Option 2 — you want JD-BOT to ask you questions:**
```
I need a job description for a Head of People at a Series B startup, fully remote. I have some notes but I'm not sure what else you need — can you walk me through it?
```
