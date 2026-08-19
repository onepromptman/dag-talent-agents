---
agent: Talent Intelligence Map Expert
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# ATLAS — Talent Intelligence Map Expert: Context Guide

## What it does

ATLAS researches the job market for any role in any industry and delivers a **Talent Intelligence Map** — a single, decision-ready document showing you how tight supply is, where talent lives, what competitors are doing, and exactly what sourcing posture to take. You use it to align with hiring managers before you post a req, to defend your timeline, or to set realistic expectations on comp.

---

## What you get back

- **Executive Summary** — one-paragraph verdict: market classification (Critical / Tight / Moderate / Loose), the supply-to-demand ratio, and the top recommended action
- **Macro Labor Market** — national and industry-level context with dated figures
- **Supply Analysis** — a talent funnel showing how the addressable pool narrows to your real target segment, plus a breakdown by experience level
- **Demand Analysis** — how many roles like yours are open right now and what competitors are actively hiring
- **Competitor Talent Capacity** — a table of 7+ employers with headcount signals and any recent trigger events (layoffs, hiring freezes, return-to-office mandates) that open up their talent
- **Geographic Intelligence** — talent density across 5+ metros, relocation notes
- **Compensation Intelligence** — market rate ranges by level drawn from at least 2 independent sources, with a positioning call

Typical format: a structured markdown document, roughly 1,500–2,500 words, heavily tabular. Every statistic includes a source and a date.

---

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | Required | None — it's on by default | N/A |
| ATS connection (your job-tracking system) | Optional | One-time setup by whoever built the Project — see "To connect your ATS" below | ATLAS asks you to type in how many open roles you have; map still runs fully |

---

## What to give it before you start

### Required

| Input | What it means | Example |
|---|---|---|
| Role title | The job you're mapping — be specific | "Senior Product Designer", not just "Designer" |
| Industry or sector | The market the company competes in for talent — this sets the competitor list | "Fintech", "B2B SaaS", "Healthcare IT" |

### Optional (each one sharpens the output)

| Input | What it means (plain English) | Example |
|---|---|---|
| Hiring location(s) | Where you need the person to be; say if remote is allowed | "NYC preferred, open to remote US" |
| Company context | Your company's size and how your pay compares to market | "Series C, ~300 people, we aim to pay at the 75th percentile" |
| Work-authorization requirement | Whether the hire must already have the right to work in a specific country — only include this if it's a real constraint | "Must be authorized to work in the US" |
| Known competitors | Companies you already know compete for this talent — ATLAS will find more, but your list anchors it | "Stripe, Plaid, Brex, Marqeta" |
| Current open-role count | How many of these roles your company has open right now (used for the supply-demand ratio) | "We have 3 open reqs" |

---

## How to format your inputs

- **Type it the way you'd describe the role to a new teammate.** Full sentences are fine; you don't need a special format.
- **Don't paste a full job description.** Title + level + industry is all ATLAS needs to start — a 10-page JD adds noise, not signal.
- **Be specific on location.** "Remote" is not enough if there are geographic restrictions. Say "remote US" or "NYC or Chicago, no relocation."
- **If you don't know a detail, skip it.** ATLAS will either research it or ask you — it won't stall.
- **Don't round-trip your own assumptions back in.** If you're not sure which companies compete for this talent, leave it blank — that's ATLAS's job.

---

## When to refresh

- A new req opens for this role (especially if it's been more than 60 days since the last map)
- You get a surprise from the market — unexpected candidate dropouts, comp counters way above your bands, a competitor just announced layoffs
- The market classification matters to a business decision (headcount plan, offer approval, timeline commitment to a hiring manager)
- Quarterly, for hard-to-fill roles you hire continuously

**Output shelf life:** A Talent Intelligence Map is reliable for roughly 60–90 days for stable roles; 30 days or less for hypergrowth or AI-adjacent roles where the landscape shifts fast. Compensation data degrades fastest — that's the first section to re-pull.

---

## Start here

Copy and paste either of these into a new ATLAS conversation as your opening message:

> "Build a talent intelligence map for a Senior Backend Engineer in fintech, hiring in NYC and open to remote US. We're a Series B company, about 200 people, and we try to pay at the 60th percentile."

> "I have 3 open Staff ML Engineer roles in the Bay Area. Map the market — who are the competitors, how tight is supply, and what sourcing posture should I take?"

**To connect your ATS:** Ask the person who set up ATLAS for your team — they'll enable the connection so ATLAS can pull your open roles automatically instead of asking you each time.
