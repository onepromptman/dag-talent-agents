---
agent: Role Comprehension & Requirement Enrichment Expert
version: a4-v1
guide-for: Claude Project / custom GPT
audience: non-technical recruiters and TA leaders
---

# SENSEI — Context Guide

## What it does

SENSEI turns any raw job description or role title into a complete **Educational Brief** — a recruiter-ready document that teaches you the role, the terminology, where to find the talent, and how to talk credibly to candidates and hiring managers before you've ever worked this type of search before.

## What you get back

- **Executive Summary** — 2-3 sentences you can recite before a hiring manager kickoff call
- **Role Overview** — plain-English explanation of what the person actually does day-to-day, plus an analogy you can repeat on a sourcing call
- **Technical Concepts Decoded** — every major term explained simply, with analogies and a guide for how deep you need to go ("mention it / understand it / discuss it")
- **Requirement Classification** — every stated requirement labeled as MUST-HAVE, NICE-TO-HAVE, or EXCLUSION, with rationale
- **Cross-Industry Talent Pool Map** — where the same skills exist under different titles in other industries, and how hard the transfer is
- **Tools & Technology Stack** — what each tool does in plain English, who uses it, and whether it's required or optional
- **Education & Career Pathways** — which degrees are relevant, what alternative paths (military, bootcamp, adjacent roles) are viable
- **Keyword Taxonomy & Boolean String** — primary/secondary keywords, title synonyms by industry, exclusion terms, and a ready-to-paste Boolean search string
- **Conversation Playbook** — credibility builders, follow-up questions, rapport topics, and landmines to avoid on sourcing calls
- **Hiring Manager Alignment Questions** — 5 targeted kickoff questions to surface scope gaps and unstated must-haves before you start searching

Typical format: one structured document organized in 10 numbered sections, with tables for requirements and skills, bullet lists for keywords, and plain prose for narratives.

## What it needs to run

| Capability | Required? | Setup needed? | If not connected |
|---|---|---|---|
| Web search | Required | None — on by default in Claude Projects | Cannot populate technical context, industry data, or tool landscape for unfamiliar roles; output quality drops significantly |
| Your internal leveling framework | Optional | Upload as a document to the Project's knowledge | SENSEI uses generic market-level seniority bands instead of your internal bands |
| A list of roles you hire frequently | Optional | Upload as a document to the Project's knowledge | SENSEI starts from scratch on each role rather than pre-populating synonyms faster |
| Internal "what good looks like" rubrics | Optional | Upload as a generic, non-identifiable document | SENSEI uses general best practices; assessment guidance will be role-generic, not team-specific |

No connection to your ATS, HRIS, or any other system is required. SENSEI works from the job description text you paste directly into the conversation.

## What to give it before you start

**Required inputs** — SENSEI will ask for these if you skip them:

| Input | What it means | Example |
|---|---|---|
| Role title | The exact title you are hiring for | "Senior Product Designer" |
| Industry or sector | The industry the company operates in — this determines which title synonyms and adjacent talent pools are relevant | "Fintech" / "Healthcare SaaS" / "Defense" |
| Seniority level | Where this role sits on your leveling ladder | "Senior" / "Staff" / "Principal" / "Mid-level" |
| Job description or key requirements | The full JD text, a link, or a verbal description of what the role needs to do | Paste the JD directly, or describe: "We need someone who can own the data pipeline end-to-end and mentor two junior engineers" |

**Optional inputs** — not required, but each one meaningfully sharpens the output:

| Input | What it means | Example |
|---|---|---|
| Company context | Size, growth stage, mission, or culture notes — helps calibrate which requirements actually matter here vs. what a generic JD lists | "Series B startup, 80 people, fast-paced, no bureaucracy" |
| Known must-haves from the hiring manager | Anything the HM has already said is non-negotiable — paste verbatim so SENSEI captures it exactly | "Must have led a team of at least 3 engineers" |
| Known dealbreakers or exclusions | Anything the HM has already ruled out | "No candidates from pure agency backgrounds" |

## How to format your inputs

- **Paste the full JD text** if you have it. More detail produces a more precise brief. A one-paragraph summary still works, but SENSEI will make more assumptions.
- **Be specific about seniority.** "Senior" means different things in a 20-person startup vs. a 5,000-person company. If your internal band name differs from the market term, say both: "We call it L5 — roughly equivalent to Senior in the market."
- **Quote the hiring manager directly** when sharing must-haves or dealbreakers. Write: "HM said 'must have production ML experience' and ruled out anyone without a CS degree." SENSEI will label these as-stated rather than reinterpreting them.
- **Describe the company like you would to a new teammate.** You do not need to format anything. A sentence like "It's a Series B healthcare AI company, about 120 people, very mission-driven, they care a lot about communication skills" is exactly what SENSEI needs.
- Don't worry about technical accuracy in what you write — SENSEI's job is to translate the technical side for you. Send whatever you have; it will fill in what you are missing via research.

## When to refresh

Re-run SENSEI when any of the following happen:

- The hiring manager significantly changes the scope, level, or must-haves after the initial brief
- The role has been open more than 90 days and you are pivoting the search strategy
- You are re-opening a role that was filled or cancelled more than 6 months ago (market context and tool landscape may have shifted)
- You are running the same role in a new industry or geography where talent pools and title conventions differ
- A candidate conversation reveals that the original brief missed a key concept, tool, or distinction

Output shelf life: 3-6 months for most roles; refresh sooner in fast-moving technical domains (AI/ML, cloud infrastructure, new regulatory areas) where tools and expectations shift quickly.

## Start here

Copy either opener as-is and paste it into SENSEI to begin:

**Starter 1 — you have a JD ready to paste:**
> "Build an educational brief for a [Seniority] [Role Title] in [Industry]. Here is the job description: [paste JD]"

**Starter 2 — you are starting from a title and a conversation:**
> "I'm kicking off a search for a [Seniority] [Role Title] at a [Company Size / Stage] [Industry] company. I don't have a full JD yet — the hiring manager told me [brief description of what they said]. Help me understand the role and where to find the talent."
