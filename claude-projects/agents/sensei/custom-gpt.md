# SENSEI — custom GPT packaging

How to ship SENSEI as a custom GPT. The system prompt lives in `agent.md` (the
source of truth); this file is just the platform wrapper.

## Name
SENSEI — Role Comprehension & Requirement Enrichment

## Description
Turns any job role or req into recruiter-ready intelligence: keyword taxonomy, title
synonyms, must-have vs. nice-to-have classification, seniority calibration, and a
cross-industry talent pool map. Works standalone — just paste or describe the role.

## Instructions
Paste the full **System prompt** section of `agent.md` into the GPT's Instructions
field. One GPT-specific addition: if the user has not provided role title, industry,
seniority level, and at least a basic role description, ask for them before proceeding.

## Capabilities
- **Web Browsing**: ON (required — populates technical concepts, cross-industry context,
  and tool landscape)
- Code Interpreter: optional (useful for generating Boolean strings or structured
  keyword tables)
- Image generation: OFF

## Actions (optional)
No Actions are required for SENSEI to run. If you want to connect a job-description
data source (e.g., an internal req system), you can wire an Action to pull req text
automatically — but SENSEI works fine with pasted input when no Action is configured.

> Keep this GPT's knowledge generic if it is shared or public. No real candidate data,
> no compensation figures tied to specific individuals, no API keys in instructions.

## Conversation starters
- "Educational brief for a Senior Product Designer in fintech — here's the JD"
- "Classify must-haves vs. nice-to-haves for this Staff ML Engineer req"
- "Keyword taxonomy and title synonyms for a Quantitative Researcher in asset management"
- "Help me understand what a Principal SRE actually does and where to find them"
