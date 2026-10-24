# What to capture

A handoff is a briefing, not a log. Its reader is an agent that knows nothing about the last session and should be productive within a minute. Put each item in the section described in [the handoff format](handoff-format.md).

## Include

- **Decisions the user made** that the code does not show: chosen approaches, rejected ones and why, scope limits.
- **Standing constraints**: protected branches, "do not change the look", required approvals, files not to touch.
- **Unfinished work** with its exact location and the next concrete action.
- **Verification state**: which checks ran, their result, and what was not checked.
- **Environment traps** that cost time: memory limits, ports, slow builds, commands that need special flags.
- **Pointers** to the documents and files that hold detail.

## Exclude

- Secrets of any kind: API keys, tokens, passwords, one-time login codes, private keys, connection strings.
- Personal data about users, clients or third parties beyond what the work needs (a name in an approval note is fine; contact details are not).
- Content that already lives in the repository: copy a link, not the text.
- Step-by-step narrative of what happened; keep only the outcome.
- Finished items that need no follow-up.
- Guesses presented as facts. Mark uncertainty plainly ("not yet confirmed on device").

## Keep it current

- Rewrite the whole file each time; do not append.
- Remove next steps that are done, and questions that are answered.
- Update the date and the verification state every time.
- If a constraint changed during the session, replace the old one; never leave both.

## Before saving, check

- Could a new agent start the first next step without asking anything?
- Is every constraint the user stated this session recorded?
- Does the file contain anything that would be harmful if the repository became public? Remove it.
