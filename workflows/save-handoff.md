# Save a handoff

Use when the user asks for a handoff, to wrap up, or to save where things stand. The result is a rewritten `HANDOFF.md` that the next session can act on immediately.

## Steps

1. **Gather the facts.** Read the current `HANDOFF.md` if there is one, then `git status`, `git log --oneline -20`, and the current branch. Note any checks you ran this session and their results.
2. **Recall the session.** List what the user decided, what changed, what is unfinished, which constraints they stated, and what slowed you down.
3. **Write the file.** Rewrite `HANDOFF.md` in place from [the template](../assets/handoff-template.md), following [the handoff format](../references/handoff-format.md). Apply [what to capture](../references/what-to-capture.md): carry over still-open items, drop finished ones, replace changed constraints.
4. **Check it.** Under about 80 lines; the first next step is actionable without questions; no secrets, tokens, one-time codes or personal data; the date is today's.
5. **Make sure agents will find it.** If the repository's agent instructions have no handoff rule, follow [Bootstrap a repository](bootstrap-repository.md) step 3.
6. **Commit when allowed.** If commits are allowed in this session, commit `HANDOFF.md` on its own (and the instructions file if step 5 changed it), following the repository's commit rules, for example `docs(handoff): update the session handoff`. Never commit to a branch the user said to avoid. Push only if the user's standing instructions allow it.
7. **Report.** Show the user the new file, or a short summary of what changed in it.

## Done when

- `HANDOFF.md` reflects the end of this session, not an earlier one.
- A new agent could start work from it without reading the conversation.
