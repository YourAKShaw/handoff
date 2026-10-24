---
name: handoff
description: Save or resume a session handoff in HANDOFF.md at the repository root, so the next session with any AI agent continues from exactly where this one stopped. Use when the user types /handoff, says "handoff", "update the handoff", "wrap up", "save where we are", or asks to continue from the last session.
---

# Handoff

Carry work from one session to the next through a single file, `HANDOFF.md`, at the repository root. Whichever agent opens the repository next — Claude Code, Codex, Gemini CLI, Antigravity, Grok, or another — reads that file first and continues from it. It holds only what a fresh session needs, and points to files instead of copying them.

## Start here

1. Decide which job the user asked for:
   - **Resume** — a new session, the user says "continue", or the repository has a `HANDOFF.md` you have not read yet.
   - **Save** — the user asks for a handoff, to wrap up, or to save where things stand.
   - **Bootstrap** — the repository has no `HANDOFF.md` or no handoff rule in its agent instructions.
2. Read the matching workflow below, then follow [the handoff format](references/handoff-format.md) for the file's shape.
3. Apply [what to capture](references/what-to-capture.md) when deciding what goes in and what stays out. Never record secrets, tokens, one-time codes or personal data.

## Choose the workflow

| Requested outcome | Read | Expected result |
|---|---|---|
| Continue from the last session | [Resume a handoff](workflows/resume-handoff.md) | Work picks up at the first open step, with the recorded constraints respected |
| Save the session for next time | [Save a handoff](workflows/save-handoff.md) | `HANDOFF.md` rewritten in place, short, current, and committed when allowed |
| Set a repository up for handoffs | [Bootstrap a repository](workflows/bootstrap-repository.md) | `HANDOFF.md` plus a short rule in the repository's agent instructions |

## Resources

- [Handoff format](references/handoff-format.md): the five sections, their order, and length limits.
- [What to capture](references/what-to-capture.md): include, exclude, and how to keep it current.
- [Agent setup](references/agent-setup.md): installing the skill globally for each agent, and the rule text for agents without skills.
- [Handoff template](assets/handoff-template.md): a ready `HANDOFF.md` skeleton.
- [Agent instructions snippet](assets/agent-instructions-snippet.md): the rule to add to `AGENTS.md`, `CLAUDE.md` or `GEMINI.md`.

## Rules that always apply

- `HANDOFF.md` is rewritten, never appended to. Old, finished items are removed, not archived.
- Keep it under about 80 lines. A long handoff defeats its purpose.
- Respect the repository's own instructions and the user's standing constraints (protected branches, commit conventions, what not to touch). Record those constraints in the handoff so the next session keeps them.
- Commit the file only when commits are allowed in the session, on its own, following the repository's commit rules.

## Validate the package

Run `python3 scripts/validate-skill.py` from this directory (Python 3.9+, standard library only), or the [shell](scripts/validate-skill.sh) or [PowerShell](scripts/validate-skill.ps1) wrapper. The [validator](scripts/validate-skill.py) checks the manifest, required files, local links and anchors, and that every resource is reachable from this file. After changing the validator, run its [regression suite](scripts/test_validate_skill.py).
