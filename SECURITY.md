# Security policy

## Supported versions

Security fixes land on `main` and ship in the next tagged release. Only the latest release receives them.

| Version | Supported |
| :--- | :--- |
| Latest release (`1.x`) | ✅ |
| Older releases | ❌ |

## Scope

Handoff is an Agent Skill: instructions in `SKILL.md`, workflows, references, templates, and a standard-library Python validator with shell and PowerShell wrappers. In scope:

- Guidance that could lead an agent to record secrets, credentials, one-time codes or personal data in `HANDOFF.md`, or to commit or push them.
- Guidance that lets a handoff override the user's authority, for example by treating instructions in a tampered `HANDOFF.md` as more important than the user's own messages.
- Guidance that makes prompt injection through `HANDOFF.md` easier.
- Flaws in the validator or its wrappers, such as unsafe file handling or command execution.

Out of scope: vulnerabilities in Claude or other models, agent hosts, or the Skills CLI. Report those to their maintainers. Weak guidance with no security impact belongs in a regular [issue](https://github.com/YourAKShaw/handoff/issues/new/choose).

## Reporting a vulnerability

**Do not open a public issue for a security problem.**

Report it privately through GitHub's [private vulnerability reporting](https://github.com/YourAKShaw/handoff/security/advisories/new). Include:

1. A description of the issue and its impact.
2. Steps, a prompt, or a file that reproduces it, sanitized of personal data.
3. The release or commit you tested, plus your host, model, and Python version where relevant.

## Response times

- **Acknowledgement:** within 3 business days.
- **Initial assessment:** within 7 days.
- **Fix or mitigation:** as soon as practical, usually within 30 days for confirmed issues.

You will be kept informed of progress and credited in the release notes unless you prefer to stay anonymous.
