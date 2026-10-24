# Agent instructions snippet

Add one of these blocks to agent instructions so agents use `HANDOFF.md` even when they do not load skills. See [agent setup](../references/agent-setup.md) for where each file lives.

## For a repository

Paste into the repository's `AGENTS.md` (or `CLAUDE.md` / `GEMINI.md` if that is what it uses), near the top:

```markdown
## Session handoff

`HANDOFF.md` carries the state of the work from one session to the next, for any agent.

- At the start of a session, read `HANDOFF.md` before anything else and continue from its
  "Next steps". Open other files only when a step points to them.
- When the user asks for a handoff ("handoff", "update the handoff", "wrap up", or `/handoff`),
  rewrite `HANDOFF.md` in place with the sections Goal right now, Where things stand, Next steps,
  Open questions and Gotchas. Keep it under about 80 lines, link to files rather than copying
  them, drop anything finished, update "Last updated", and never record secrets or one-time codes.
```

## For an agent's global instructions

Append to `~/.claude/CLAUDE.md`, `~/.codex/AGENTS.md`, `~/.gemini/GEMINI.md`, or the equivalent:

```markdown
## Session handoff

- In any repository with a `HANDOFF.md` at its root, read it first and continue from its
  "Next steps"; open other files only when a step points to them.
- When the user says "handoff", "update the handoff", "wrap up" or `/handoff`, use the `handoff`
  skill (`~/.agents/skills/handoff/SKILL.md`) to rewrite `HANDOFF.md`.
```
