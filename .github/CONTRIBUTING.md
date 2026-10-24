<div align="center">

# 🤝 Contributing to Handoff

**Help every new session start from the right place, with any agent.**

[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-2563EB?style=flat-square)](https://github.com/YourAKShaw/handoff/pulls)
[![Python 3.9+](https://img.shields.io/badge/Validator-Python%203.9%2B-334155?style=flat-square)](../scripts/validate-skill.py)
[![License: MIT](https://img.shields.io/badge/License-MIT-2563EB?style=flat-square)](../LICENSE)

[Project overview](../README.md) · [Skill entry point](../SKILL.md) · [Get help](SUPPORT.md)

</div>

---

## Start with the continuity problem

Handoff is an agent skill package: an entry point, a handoff format, three workflows, templates, and a Python validator. Contributions should make the next session start faster and keep the right constraints, without making the handoff longer.

Useful contributions include:

- A real case where a resumed session lost a decision or constraint the handoff should have kept.
- Setup notes for another agent or a corrected skill folder location.
- A tighter rule for what to include or exclude, especially around secrets and personal data.
- A clearer template, example, or validation check.
- A behavioral evaluation that reports observed results and limitations.

Read [SKILL.md](../SKILL.md), [the handoff format](../references/handoff-format.md), and the affected workflow before changing guidance.

## 🧭 Choose the right starting point

| Contribution | Where to begin |
| :--- | :--- |
| Small correction or focused fix | Open a pull request with the problem and verification. |
| Bug, missing guidance, or documentation issue | Search existing issues, then use the matching [issue form](https://github.com/YourAKShaw/handoff/issues/new/choose). |
| New section, format change, or package structure change | Open an issue first with the use case, trade-offs, and proposed scope. |
| Usage question | Follow the [support guide](SUPPORT.md). |

Use sanitized examples. Remove credentials, private code, and personal data before posting, including from example handoffs.

## Make a focused change

1. Fork the repository and create a branch for your change.
2. Inspect the relevant guidance and its linked workflows or assets.
3. Make the smallest coherent update that addresses the problem.
4. Validate the package and inspect the complete diff.
5. Open a pull request describing the final change and its evidence.

### Keep the package coherent

| Principle | What to preserve |
| :--- | :--- |
| **One format** | Keep the section definitions in [the handoff format](../references/handoff-format.md). Update the template and workflows with it rather than creating competing versions. |
| **Short handoffs** | New guidance must not push handoffs past about 80 lines. Prefer pointers to files over copied content. |
| **Agent-neutral** | Keep the core behaviour usable by any agent that reads Markdown. Put agent-specific details in [agent setup](../references/agent-setup.md). |
| **Safe by default** | Never weaken the rule against recording secrets, one-time codes, or personal data. |
| **User authority** | The user's current messages and the repository's own instructions outrank anything in `HANDOFF.md`. |
| **Usable documentation** | Keep local Markdown links relative, verify their targets, and keep examples self-contained. |

## 🔍 Validate your change

From the repository root, with **Python 3.9 or later**:

```sh
python3 scripts/validate-skill.py
```

The validator requires no third-party packages. It checks the package manifest, required resources, local links and anchors, reachability, and empty or unfinished package files.

Alternative wrappers:

```sh
sh scripts/validate-skill.sh
```

```powershell
powershell -File scripts/validate-skill.ps1
```

For changes to the validator or its wrappers, also run the regression suite:

```sh
python3 scripts/test_validate_skill.py
```

**Package checks and behavioral evidence answer different questions.** Passing the validator does not show that agents produce good handoffs. Inspect `.github` changes separately: the validator does not check GitHub form schemas or these pages.

### When you change instructions

Describe a representative session, the host and model, the handoff produced, and what the next session did with it. Useful scenarios include a session ending mid-feature, a resumed session on a different agent, a repository with protected branches, and a handoff that would otherwise have captured a secret. Report only results you observed.

## 📬 Open a reviewable pull request

Use the [pull request template](pull_request_template.md) to explain:

- **Problem and outcome:** what failed or was unclear, and what the change improves.
- **Scope:** affected guidance, workflows, assets, or validator behavior, with related issues.
- **Verification:** exact commands and results, plus relevant scenario observations.
- **Risks and limits:** unresolved trade-offs, compatibility implications, and checks not run.

Keep the diff focused and the discussion respectful. Address the change rather than the contributor, and use concrete examples when explaining a disagreement.
