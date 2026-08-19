---
agent: Interview Process Architect
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# Interview Process Architect — Context Guide

## What it does

INTERVIEW-LAB designs a complete, structured interview process for any role in any industry. Give it a role title and your must-have requirements, and it produces a ready-to-use interview plan — question banks, scoring rubrics, a coverage matrix, and a debrief protocol. It runs its own intake first, asking you a few questions before it builds anything.

## What you get back

- **Interview Funnel Summary** — all stages (Recruiter Screen through Debrief), with duration, interviewer role, and pass-rate targets per stage
- **Competency Coverage Matrix** — a table showing every skill and trait you care about, which stage assesses it, and how
- **Question Banks with Scoring Rubrics** — for every stage, including technical, behavioral (STAR), and values questions; each question comes with follow-up probes and a 4-point rubric using observable behaviors (not vague adjectives)
- **Debrief Protocol** — structured agenda, scoring aggregation template, calibration guidance, and decision rules (including what triggers an extended Strong No discussion)
- **Interviewer Prep + Bias Mitigation materials** — ready to forward to your panel before the onsite

Typical format: a single long document you can paste into a shared doc or your ATS prep section. Sections are clearly headed and interviewer-ready — no reformatting needed.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | No | None | Agent works fine without it — all inputs come through the intake conversation |
| ATS connection | No | None | Not needed — role inputs come from you directly |
| Company knowledge uploads (leveling guides, values definitions, existing plans) | Optional | Upload to Project Knowledge | Agent uses generic professional defaults if not provided |

## What to give it before you start

You don't need everything ready — the agent will walk you through an intake and ask for anything that's missing. That said, having this information at hand speeds things up.

**Required — the agent will ask for these before building anything:**

| Input | What it means | Example |
|---|---|---|
| Role title and level | The exact job title plus seniority | "Senior Product Designer" or "Staff Data Scientist" |
| Industry or sector | The field the company operates in | "B2B SaaS," "healthcare," "financial services" |
| Must-have technical skills | Hard skills or qualifications every candidate must have | "5+ years SQL," "Python," "PMP certification" |
| Must-have behavioral traits | How you need this person to operate | "Ownership," "cross-functional collaboration," "clear communicator under ambiguity" |

**Optional — each one unlocks a more tailored output:**

| Input | What it means | Example |
|---|---|---|
| Nice-to-have skills | Skills that are a plus but not a gate | "Experience with Looker," "startup background" |
| Deal-breakers | Explicit disqualifiers that must be verified | "Must be authorized to work in the US," "must not require relocation support" |
| Company values or culture dimensions | How your organization defines success beyond the role | "Integrity," "move fast," "customer obsession" — include your definitions if you have them |
| Hiring manager name or role | Personalizes the onsite schedule template | "VP of Engineering," "Sarah (Hiring Manager)" |
| Existing interview process | Any current process you want updated rather than rebuilt from scratch | Paste or describe your current stages — the agent will do a gap analysis |

## How to format your inputs

- **Paste your job description or requirement list as-is** — free text, bullet points, or a raw JD copy are all fine. The agent will extract what it needs.
- **Do list must-haves and nice-to-haves separately** if you can — it speeds up the coverage matrix step.
- **Do name deal-breakers explicitly** ("must have X" or "cannot consider candidates who Y") so they get a verification point in the plan.
- **Don't worry about formatting your values** — a plain list like "ownership, transparency, bias toward action" is enough; the agent will build scenario questions around them.
- **Don't upload real candidate data or interview notes** — this tool designs processes, not evaluates individuals. Keep scorecards in your ATS.

## When to refresh

Re-run or update the plan when:

- The role title, level, or core requirements change significantly
- Your company values or culture definition has been updated
- You receive consistent recruiter or interviewer feedback that a stage isn't working
- You're reusing a plan for a new team or org — different hiring managers may have different priorities worth capturing
- More than 6 months have passed since the plan was created and you're actively hiring on it

Output shelf life: plans are point-in-time snapshots. For active, ongoing hiring, review the plan at the start of each new candidate cycle.

## Start here

Copy and paste either of these openers to get started immediately:

---

**Option 1 — start from scratch:**

> Design an interview plan for a [Senior / Staff / Lead] [Job Title] at a [industry] company. Here are my must-haves: [paste your list]. Deal-breakers: [paste any]. Nice-to-haves: [paste any]. Values to assess: [paste any].

---

**Option 2 — update an existing process:**

> I have an existing interview process for a [Job Title] role. Can you do a gap analysis and update it? Here's what we currently do: [describe or paste stages]. Must-have requirements: [paste list]. Values to assess: [paste any].

---
