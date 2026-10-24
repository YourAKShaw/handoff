# Agent setup

Install the skill once, globally, and every repository can use it. Agents that support Agent Skills load it directly; agents that do not get the same behaviour from a short rule in their global instructions, using [the snippet](../assets/agent-instructions-snippet.md).

## One shared copy

Keep a single copy of the package and link it into each agent's skill folder, so an edit updates every agent:

```sh
git clone https://github.com/YourAKShaw/handoff.git ~/.agents/skills/handoff
```

`~/.agents/skills` is the shared location several agents read. Link the copy into the others:

| Agent | Skill folder | Global instructions file |
| :--- | :--- | :--- |
| Codex | `~/.agents/skills/handoff` (reads it directly) | `~/.codex/AGENTS.md` |
| Claude Code | `~/.claude/skills/handoff` | `~/.claude/CLAUDE.md` |
| Gemini CLI | `~/.gemini/skills/handoff` | `~/.gemini/GEMINI.md` |
| Antigravity | `~/.gemini/antigravity/skills/handoff` | `~/.gemini/GEMINI.md` |
| Other agents | their skill folder, if any | their global instructions file, if any |

```sh
ln -sfn ~/.agents/skills/handoff ~/.claude/skills/handoff
mkdir -p ~/.gemini/skills ~/.gemini/antigravity/skills
ln -sfn ~/.agents/skills/handoff ~/.gemini/skills/handoff
ln -sfn ~/.agents/skills/handoff ~/.gemini/antigravity/skills/handoff
```

Skill folder locations differ between agent versions; check each agent's documentation if a folder above is not picked up. On Windows, copy the folder instead of linking it, or use a directory junction.

## Global rule for every agent

Add the [agent instructions snippet](../assets/agent-instructions-snippet.md) to each global instructions file in the table. It makes agents read `HANDOFF.md` first in any repository that has one, and use this skill when asked for a handoff. Append it; do not overwrite rules already in those files.

## Skills CLI

Agents supported by the Skills CLI can install the package with:

```sh
npx skills add YourAKShaw/handoff --global
```

## Check the installation

1. Run `python3 ~/.agents/skills/handoff/scripts/validate-skill.py`.
2. Open a repository that has a `HANDOFF.md` with a new session and say "continue". The agent should read `HANDOFF.md` first and start from its first next step.
3. Ask for a handoff. The agent should rewrite `HANDOFF.md` in the [handoff format](handoff-format.md).

In Claude Code, `/handoff` appears among the slash commands once the skill is installed.
