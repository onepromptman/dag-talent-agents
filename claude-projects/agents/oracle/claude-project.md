# ORACLE — Claude Project packaging

How to ship ORACLE as a Claude Project. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Project name
ORACLE — Benchmark & Reference Retrieval

## Description
Retrieves and synthesizes hiring benchmarks, market reference points, and
process/quality standards from public industry reports or user-supplied docs.
Every data point is cited, dated, and confidence-rated.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your own comp benchmarks or leveling guide (ORACLE will search these first)
- Industry salary surveys or funnel-conversion studies you've licensed
- Any internal pipeline reports you want ORACLE to reference (keep generic if the
  Project is shared — no candidate-level data)

> Do NOT upload real candidate data or any export-controlled content to a shared
> Project. Internal benchmarks containing personal data should stay off shared
> Projects.

## Connections / tools
- **Web search** enabled (required for Tier 2 public-report retrieval).
- No ATS connection required; if you want ORACLE to factor in live open-req
  counts, paste them in the conversation.

## Conversation starters
- "What are current offer-acceptance-rate benchmarks for senior engineers in tech?"
- "Give me funnel conversion benchmarks for sales roles — SDR to AE pipeline."
- "What's the benchmark time-to-fill for product managers? I'm hiring in a 500-person company."
- "Pull outreach benchmarks: InMail open rates and reply rates for technical recruiting."
