# Bootstrap a repository

Use when a repository has no `HANDOFF.md`, or its agent instructions do not mention it.

## Steps

1. **Look first.** Check for an existing `HANDOFF.md`, and read the repository's agent instructions (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, or similar) and commit conventions.
2. **Create `HANDOFF.md`** at the repository root from [the template](../assets/handoff-template.md), filled in for the current state using [Save a handoff](save-handoff.md) steps 1 to 4.
3. **Add the rule** from [the agent instructions snippet](../assets/agent-instructions-snippet.md) to the repository's shared agent instructions:
   - Prefer `AGENTS.md`, which most agents read. If `CLAUDE.md` imports `AGENTS.md`, editing `AGENTS.md` is enough.
   - If only `CLAUDE.md` or `GEMINI.md` exists, add it there.
   - If none exists, ask the user before creating `AGENTS.md`.
   - Keep the rule near the top, and do not change unrelated instructions.
4. **Commit when allowed,** as one commit for `HANDOFF.md` and the rule, following the repository's commit rules.
5. **Tell the user** that new sessions in this repository will now start from `HANDOFF.md`, and that saying "handoff" (or `/handoff` in Claude Code) updates it.

## Done when

- `HANDOFF.md` exists and describes the current state.
- The repository's agent instructions tell any agent to read it first.
