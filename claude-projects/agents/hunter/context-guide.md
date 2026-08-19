---
agent: Sourcing Playbook Expert
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# HUNTER — Context Guide

## What it does

HUNTER builds a complete, ready-to-use sourcing playbook for any open role in any industry. You tell it the role and what you need; it hands back copy-paste search strings, a prioritized target company list, and personalized outreach angles — everything a recruiter needs to start filling pipeline the same day.

## What you get back

- **Candidate Persona** — a narrative description of who you are looking for (background, motivations, what would make them take your call), plus a targeting table and a list of what triggers them to move
- **Title Synonyms and Keyword Taxonomy** — the exact job titles and skills to search for, plus terms to exclude so your results stay clean
- **Search String Library** — three ready-to-paste LinkedIn Recruiter boolean strings (broad, competitor-targeted, precision passive) plus Google X-Ray strings for LinkedIn, GitHub (for technical roles), conference speakers, and university alumni
- **Target Company List** — three tiers: direct competitors to poach from, secondary employers, and adjacent industries that produce transferable talent; includes any known trigger events (layoffs, return-to-office mandates, hiring freezes) where found
- **Multi-Channel Strategy and Outreach Cadence** — which channels to use given how competitive the market is, a day-by-day follow-up sequence, and a referral brief the hiring manager can share with their team
- **Pipeline Math** — backwards calculation from hires needed all the way to how many candidates you need to contact, with every conversion-rate assumption labeled

Typical format: one structured document with numbered sections, tables, and strings formatted for direct paste into LinkedIn Recruiter or a browser search bar.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | Required | None — enabled by default in Claude Projects | HUNTER cannot research target companies or trigger events in real time; you must supply those manually |
| ATS connector (e.g., Greenhouse, Lever) | Optional | Set up through your Project's Connections settings | HUNTER asks you for open-req counts or uses industry-standard estimates; no connector needed for the core playbook |

## What to give it before you start

### Required

| Input | What it means | Example |
|---|---|---|
| Role title | The job title you are hiring for | "Senior Data Engineer" |
| Industry or sector | The field your company operates in; HUNTER uses this to research which companies hire this role | "Fintech" or "Enterprise SaaS" |
| Seniority level | How senior the role is, or a years-of-experience range | "Senior (5-8 years)" or "Staff-level, 10+ years" |
| Must-have skills | Skills a candidate must have to be considered | "Python, Spark, dbt, cloud data warehouse experience" |
| Nice-to-have skills | Skills that would strengthen a candidate but are not dealbreakers | "Streaming experience (Kafka), prior fintech background" |

### Optional (each one unlocks something)

| Input | What it means | Example | What it unlocks |
|---|---|---|---|
| Hiring location(s) and remote policy | Where the role is based and whether remote is allowed | "New York and Chicago; remote OK within the US" | Location filters on every search string; more accurate pool-size estimates |
| Company context | Your company's name, size, mission, and whether your comp is above, at, or below market | "Series C startup, ~200 employees, mission-driven, comp at market" | Personalization angles tailored to your value props instead of generic ones |
| Known target or competitor companies | Companies you already know produce the talent you want | "Stripe, Plaid, Brex, Block" | HUNTER incorporates them directly instead of researching from scratch; saves time |
| Work-authorization requirement | Whether candidates must have specific legal work authorization | "Must be authorized to work in the US without sponsorship" | Applied as a filter in string construction; HUNTER never assumes one unless you state it |
| Number of roles to fill | How many open headcount you are filling | "3 hires" (default is 1) | Pipeline math scales correctly to the actual volume you need |
| Prior sourcing data | Strings or channels that worked before, or response rates from a previous campaign | "Our last InMail campaign on LinkedIn got 8% response rate" | HUNTER calibrates pipeline math and channel priority to your actual data rather than defaults |

## How to format your inputs

- Paste your job description or a plain-English description of the role directly into the chat — HUNTER reads it and asks for anything missing.
- List must-haves and nice-to-haves as a simple comma-separated list or bullet points; no special formatting needed.
- If you have a list of target companies, paste them as-is; HUNTER will sort them into tiers.
- Do not worry about getting inputs perfect upfront — HUNTER will ask for anything it needs before producing output rather than guessing.
- Do not paste real candidate names, resumes, or personal data into the chat.

## When to refresh

Re-run HUNTER when:

- The role has been open for 60+ days and pipeline has stalled — market conditions and trigger events change
- You are expanding to a new location or removing a location restriction
- A major trigger event occurs in the market (a large competitor announces layoffs or a hiring freeze)
- You are opening a net-new role type you have not sourced before
- Response rates have dropped significantly from the baseline the playbook projected

Output shelf life: 60-90 days for most markets; 30 days or less in fast-moving markets or when the talent pool is small.

## Start here

Paste either of these directly into HUNTER to get a full playbook:

**Option 1 (full context):**
> "Build a sourcing playbook for a Senior Data Engineer in fintech. We're hiring in New York and the role is remote-eligible within the US. Must-haves: Python, SQL, dbt, and experience with a cloud data warehouse (Snowflake or BigQuery). Nice-to-haves: Kafka or Flink experience, fintech domain knowledge. We need to hire 2 people. Our comp is at market."

**Option 2 (minimal — HUNTER will ask follow-up questions):**
> "Build a sourcing playbook for a Head of Growth at a Series B SaaS company. I need boolean strings and a target company list."
