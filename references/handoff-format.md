# Handoff format

`HANDOFF.md` lives at the repository root. It is plain Markdown that any agent or person can read without tools. Start from [the template](../assets/handoff-template.md).

## Header

Two lines before the first section:

1. One sentence saying the file is read first and rewritten at the end of a session.
2. `Last updated: YYYY-MM-DD`.

## The five sections

Use these headings, in this order. Omit a section only when it would be empty, and say so in one line rather than leaving a blank heading.

### Goal right now

Two to five lines. The user's current aim, in their terms, and the standing constraints that shape all work: things they asked never to change, branches never to touch, approvals still required. Link the source documents (brief, issue, spec) instead of summarising them.

### Where things stand

- The working branch and its remote.
- What is finished, in a sentence or two, with a pointer to where the detail lives (a changelog, `git log`, a tracking file).
- The result of the last checks actually run, with the command. Say plainly when checks were not run.

### Next steps

A numbered list, most important first. Each step names where to start — a file and the problem in it, or an exact command — so the next session can begin without searching. Keep each step to one to three lines.

### Open questions

Decisions waiting on the user, a client, or another team, and anything blocked on access the agent does not have.

### Gotchas

Traps a fresh session would otherwise hit: environment limits, slow or flaky tools, commands that must be run a certain way, conventions that are easy to miss. Only include what has actually bitten, or would.

## Length and style

- Under about 80 lines. If it grows past that, it is carrying history; cut finished work.
- Short sentences, plain words, no tables unless they are clearly easier to scan.
- Link with relative paths from the repository root.
- Write facts and decisions, not narrative. "Card height bug in `GuidePage.tsx`: remove `height: '100%'`" beats "we spent a while on the guide page".
