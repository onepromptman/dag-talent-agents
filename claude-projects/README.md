# DAG Talent Agents — Claude Projects & Custom GPTs

A roster of **standalone, single-job expert agents** for recruiters and Talent
Acquisition teams. Each one runs on its own — no setup, no other agents required —
asks you for what it needs, and works in **any industry** (you supply the
industry/company context at runtime).

> **Looking for Talent One, the coordinated kit?** It grew out of this roster and
> graduated to its own repo:
> **[onepromptman/talent-one](https://github.com/onepromptman/talent-one)** —
> eleven coordinated agents, one role brief in, a full eight-document hiring
> package out, shipped as a Claude Code / Cowork plugin.

Each agent ships in three drop-in forms plus a guide to feed it well:

| File | What it is |
|---|---|
| `agent.md` | The core system prompt (the "brain") + spec |
| `claude-project.md` | Paste-in setup for a **Claude Project** |
| `custom-gpt.md` | Paste-in setup for a **custom GPT** |
| `context-guide.md` | How a non-technical recruiter feeds it for **max performance** |

## The roster

| Codename | What it does | Deliverable |
|---|---|---|
| **ATLAS** | Talent intelligence — market supply/demand for a role | Talent Intelligence Map (sourced, dated) |
| **SENSEI** | Role comprehension & requirement enrichment | keywords, synonyms, must/nice, talent pools |
| **ORACLE** | Benchmark & reference retrieval (generic, public sources) | sourced benchmark data with confidence |
| **HUNTER** | Sourcing playbook | persona, search strings, target list, personalization |
| **SHAKESPEARE** | Candidate outreach campaign | multi-touch sequence + message drafts |
| **JD-BOT** | Job description writer (its coordinated successor ships inside [Talent One](https://github.com/onepromptman/talent-one)) | bias-checked, conversion-oriented JD |
| **INTERVIEW-LAB** | Interview design (runs its own intake) | stage plan, question bank, scoring rubrics |
| **INTERVIEW-COACH** | Coaches the human interviewer (legal · signal · prep · narrative · selling · scoring · bias) | pre-interview briefing + debrief assist |
| **Pforge** | Prompt engineering for recruiters | an upgraded prompt + the "why" |

## How to use one

1. Pick an agent. Open its `claude-project.md` (for Claude) or `custom-gpt.md` (for a custom GPT) and paste the setup in.
2. Read its `context-guide.md` — it tells you, in plain English, exactly what to give the agent to get the best result.
3. Start the conversation with one of the copy-paste openers at the bottom of the guide.

## Design notes

- **Generic by construction.** No real candidate, company, or hiring data. No keys.
  Every agent takes industry/company as input and asks for anything it's missing.
- **The context layer is the point.** Each agent pairs with a `context-guide.md`
  so the output quality scales with what you feed it — the difference between a
  generic answer and a sharp, decision-ready one.
- **Optional live data.** Where it helps (ATLAS, HUNTER, ORACLE), an agent can use
  a connected ATS for live reqs/funnel data; without one it simply asks you for the
  numbers and degrades gracefully.
