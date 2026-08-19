# DAG Talent Agents

Recruiting talent agents, organized by the platform they run on. Each platform
folder is a self-contained implementation; pick the one that matches how you work.

## Platforms

### `claude-projects/`
Standalone drop-in recruiting agents for Claude Projects and Custom GPTs. Each
agent is used on its own, one conversation at a time. There is no orchestration
here by design: you drop an agent into a Project or GPT and talk to it directly.
The roster covers market intelligence, role comprehension, sourcing, outreach,
JD writing, interview design, and more.

### `n8n-swarm/`
The same recruiting roster wired as an autonomous n8n pipeline (agents-as-tools).
A single webhook starts the run and the agents hand work to each other end to
end, delivering a finished result. This is the orchestrated ("DAG") variant.

## Which one to use

- Want a helper you drive yourself, one agent at a time? Use `claude-projects/`.
- Want a hands-off pipeline that runs the whole play automatically? Use `n8n-swarm/`.

Both draw on the same underlying agent roster; they differ only in platform and
in whether a human or the workflow does the orchestration.
