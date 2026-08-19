---
agent: ORACLE — Benchmark & Reference Retrieval Expert
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# ORACLE — Context Guide

## What it does

ORACLE retrieves hiring benchmarks and market reference data from public industry reports, then returns every number fully cited, dated, and rated for how closely it matches your situation. The deliverable is an **ORACLE Report** — a structured table of data points you can use immediately to ground a decision, set a goal, or push back on a stakeholder.

## What you get back

- **Data Points** — the actual numbers (conversion rates, time-to-fill, offer acceptance, compensation ranges, outreach reply rates, etc.) in a table or list
- **Source Attribution** — one row per data point showing exactly where the number came from and how old it is
- **Confidence rating** — HIGH (exact match to your role/industry), MEDIUM (close proxy), or LOW (aggregate only — use with caution)
- **Conflict flags** — when two sources disagree on the same metric, ORACLE calls it out rather than picking one silently
- **Application Notes** — 1-3 sentences on what to assume and what to calibrate before you use the data

Typical format: structured markdown report with labeled sections; paste directly into a deck, doc, or stakeholder email.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | Required | None — enabled by default in Claude Projects | ORACLE can only use docs you paste in; it cannot pull current public reports |
| Your own reference documents (comp surveys, licensed reports, internal pipeline data) | Optional | Upload or paste into the conversation | ORACLE researches public benchmarks instead — still useful, just less specific to your context |

## What to give it before you start

**Required**

| Input | What it means | Example |
|---|---|---|
| Query | The specific benchmark or data point you need | "What is the average offer acceptance rate for software engineers?" |
| Role family / function | The job category you are hiring for | Software engineering, sales, finance, operations, product |

**Optional — each one narrows the results and increases confidence**

| Input | What it means | Example | Unlocks |
|---|---|---|---|
| Industry / sector | The market segment you operate in | Technology, healthcare, financial services, manufacturing | Industry-split benchmarks instead of cross-market averages |
| Company size band | How big your organization is | Under 100 employees, 100-499, 500-999, 1,000+ | Size-band benchmarks (conversion rates differ significantly by company size) |
| Seniority level | The level of the role | Junior, mid-level, senior, staff or above | Level-split data — especially important for compensation and time-to-fill |
| Reference documents | Your own surveys, reports, or internal pipeline exports | A comp survey PDF, a licensed funnel-conversion study, a salary band spreadsheet | ORACLE searches your docs first; they become the highest-authority source in the report |

> **Note on reference documents:** you do not need to supply them. If you have none, ORACLE goes straight to public industry reports (Gem, Ashby, SHRM, LinkedIn Talent Solutions, Payscale, CoderPad, BLS, and others). Supplying your own docs simply means the numbers will reflect your specific data before falling back to public benchmarks.

## How to format your inputs

- **Do** write your query as a plain question or statement — "What are current time-to-fill benchmarks for product managers?" works perfectly.
- **Do** include role, industry, size, and level in the same message if you have them — ORACLE applies every filter you give it.
- **Do** paste or upload reference documents before you type your query if you want ORACLE to search them.
- **Don't** write your query as a giant paragraph of context — one clear ask plus a few filter details is ideal.
- **Don't** worry about formatting your inputs as a form or table — plain text is fine.

## When to refresh

Re-run ORACLE when any of the following happen:

- More than 6 months have passed since your last pull (benchmark reports publish annually; labor-market data shifts faster)
- You are hiring into a new role family, industry, or company-size band not covered by a previous report
- A stakeholder challenges a number you are using and you want a second, current source
- You are starting a new recruiting planning cycle and need fresh baselines

**Output shelf life:** benchmark data from public reports is typically 6-18 months reliable. ORACLE flags any data point older than 18 months with a DATA_VINTAGE_WARNING. Compensation data goes stale fastest; funnel conversion rates are more stable year-over-year.

## Start here

Copy either opener as-is and paste it into ORACLE to get your first report.

**Option 1 — quick pull, no filters:**
```
What are current offer acceptance rate benchmarks for mid-level software engineers? Use the most recent public industry data available.
```

**Option 2 — filtered pull with context:**
```
I need time-to-fill benchmarks for senior sales roles (account executive level) at a company with 200-500 employees. Industry is SaaS / technology. Pull the most recent data you can find and flag anything older than 18 months.
```
