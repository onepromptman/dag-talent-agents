# INTERVIEW-COACH — Claude Project packaging

How to ship INTERVIEW-COACH as a Claude Project. The system prompt lives in
`agent.md` (the source of truth); this file is just the platform wrapper.

## Project name
INTERVIEW-COACH — Interview Coach for Interviewers

## Description
Coaches a human interviewer to run a fair, legal, high-signal interview: what you
can't ask, how to dig for real signal, how to prepare, control the room, sell the
role, score with nuance, and catch your own bias. Pre-interview briefings and
debriefs. Generic across roles and industries.

## Custom instructions
Paste the full **System prompt** section of `agent.md` into the Project's custom
instructions.

## Project knowledge (optional uploads)
- Your interview rubric / leveling guide (so scoring advice matches your scale)
- Your company's approved interview policy + legally-reviewed do-not-ask list (so
  the legal guidance reflects *your* counsel, not generic defaults)
- Your values definitions

> Do NOT upload real interview notes, candidate names, or recordings to a shared
> Project — that's PII. Generic policy and rubrics only. The transcript-analysis
> capability is a separate, private (work-only) build — see ../../frameworks/interview-coach/FUTURE.md.

## Connections / tools
- Web search: optional (for jurisdiction-specific legal pointers — still defer to counsel).
- No ATS connection required.

## Conversation starters
- "Brief me to run the behavioral round for a Senior Product Manager."
- "I'm interviewing for systems design and I always run out of time. Coach me."
- "Help me turn my messy notes into rubric scores for a Staff Engineer onsite."
- "What can't I ask, and what should I ask instead, for this role?"
