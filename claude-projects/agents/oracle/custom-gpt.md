# ORACLE — custom GPT packaging

How to ship ORACLE as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
ORACLE — Benchmark & Reference Retrieval

## Description
Retrieves cited, dated hiring benchmarks and market reference data from public
industry reports. Funnel conversion, time-to-fill, offer acceptance, comp
trends, outreach rates, source yields — grounded, not guessed.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided a query and at
least a role family, ask for them before researching.

## Capabilities
- **Web Browsing**: ON (required for Tier 2 public-report retrieval)
- Code Interpreter: optional (useful for computing derived metrics or building a
  benchmark comparison table from multiple sources)
- Image generation: OFF

## Knowledge (optional file uploads)
Upload your own benchmark docs, salary surveys, or funnel reports. ORACLE will
search these before going to the web. Keep uploads generic if this GPT is shared
— no real candidate data, no confidential headcount files.

> No API keys in instructions. No export-controlled content in uploads.
> Keep this GPT's knowledge generic if it is shared or public-facing.

## Conversation starters
- "Offer acceptance rate benchmarks for senior engineers — tech industry"
- "Funnel conversion rates: what's a good app-to-screen rate for sales roles?"
- "InMail and cold-email outreach benchmarks for technical recruiting"
- "Time-to-fill benchmarks for product roles at a mid-size company"
