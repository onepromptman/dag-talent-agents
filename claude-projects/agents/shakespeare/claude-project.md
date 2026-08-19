# SHAKESPEARE — Claude Project packaging

How to ship SHAKESPEARE as a Claude Project. The system prompt lives in `agent.md`
(the source of truth); this file is just the platform wrapper.

## Project name
SHAKESPEARE — Outreach Campaign Architect

## Description
Designs multi-touch candidate outreach campaigns for any role in any industry:
sequence cadence, channel mix, ready-to-send connection notes and emails,
personalization framework, and value-prop framing. Standalone — no upstream agents
required.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your company's approved messaging guidelines or proof points document (so
  SHAKESPEARE draws from verified facts rather than asking every session)
- A competitor / target-employer pain-point map for your most common talent pools
  (so employer-type angles are pre-loaded)
- Your historical reply-rate benchmarks by channel and seniority (so performance
  benchmarks are calibrated to your actual data, not industry averages)

> Do NOT upload real candidate data or anything export-controlled to a shared
> Project. Candidate-specific information should come from the recruiter at runtime,
> not as static uploads.

## Connections / tools
- **Web search** enabled (recommended for personalization research — finding recent
  projects, publications, or news about a specific candidate or their employer).
- No ATS connection required. SHAKESPEARE asks the recruiter for role and persona
  context directly; it does not pull live pipeline data.

## Conversation starters
- "Build outreach templates for a Senior Data Engineer pipeline — candidates coming from big tech, motivated by ownership and mission."
- "Write a personalized InMail to someone who just shipped a major open-source project and works at a late-stage startup."
- "I need a 5-touch sequence for a Principal ML Engineer role. Drought market, highly recruited persona."
- "Refresh this connection note — the hook isn't landing and the CTA is too soft."
