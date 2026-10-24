# Resume a handoff

Use at the start of a session in a repository that has a `HANDOFF.md`, or when the user says "continue".

## Steps

1. **Read `HANDOFF.md` first,** before exploring the repository. If it does not exist, say so and offer [Bootstrap a repository](bootstrap-repository.md).
2. **Check it is current.** Compare its branch and "Where things stand" with `git status`, the current branch and `git log --oneline -10`. If they disagree — another branch, newer commits, missing work — tell the user what differs before acting.
3. **Adopt the constraints.** Treat "Goal right now" and "Gotchas" as standing instructions for the whole session, alongside the repository's own instructions. The user's newer messages override the file.
4. **Start the first next step.** Open only the files that step points to. Do not re-read the whole repository or re-derive decisions the file records.
5. **Raise open questions when they block you.** If a step depends on an "Open questions" item, ask the user rather than guessing.
6. **Keep notes for the next save.** As steps finish or change, remember them so [Save a handoff](save-handoff.md) can rewrite the file at the end.

## Done when

- Work continues from the recorded next step, with the recorded constraints respected.
- Any mismatch between the file and the repository has been raised with the user.
