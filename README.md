# Adversarial Engineering Skills

**Challenge the plan. Review the diff. Prove the result.**

[简体中文](docs/README.zh-CN.md) · [繁體中文](docs/README.zh-TW.md) · [日本語](docs/README.ja.md) · [한국어](docs/README.ko.md) · [Español](docs/README.es.md) · [Français](docs/README.fr.md) · [Deutsch](docs/README.de.md) · [Português (Brasil)](docs/README.pt-BR.md)

An engineering management skill for coding agents: three evidence-backed review gates that turn plausible output into inspectable engineering work. Built from a project's adversarial review practice and generalized without its private code, data or operational details.

## Why this exists

A plan can miss a consumer. A correct-looking diff can break a permission boundary. A green test suite can leave the actual user journey untested. Asking the same agent “are you sure?” does not close those gaps.

This skill separates implementation from challenge and acceptance. Reviewers must identify concrete failure paths; the primary agent must fix each blocker or reject it with evidence. “No findings” is valid. More process is not automatically more quality.

## Three gates

| Gate | When | Required outcome |
| --- | --- | --- |
| 1. Plan | Before substantive implementation | Challenge constraints, contracts, state, permissions, missing consumers and complexity. |
| 2. Change | After a coherent batch, before merge | Inspect the actual diff and affected behavior; add security review where relevant. |
| 3. Acceptance | Before completion claims | Match claims to current runnable or artifact-level evidence and disclose limits. |

Small edits get small checks. High-risk changes get independent perspectives and bounded batches. Self-review is explicitly labeled and never substitutes for a project's mandatory independent review. Unresolved blockers remain blockers. The skill does not authorize deployment or publication.

## Install

Requires Git and Node.js/npm for the Skills CLI. Run inside the project you want to equip:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Choose your agents in the interactive installer. For copy-based installation to selected agents:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering -a claude-code -a codex -a cursor --copy
```

Add `-g` for user-wide installation. See [installation options](docs/INSTALL.md) for Copilot, Gemini CLI, OpenCode, Cline, Windsurf, manual installation and removal.

The installer is the third-party [Skills CLI](https://github.com/vercel-labs/skills). Its supported-agent list is an installation compatibility list, not a claim that this project has tested every agent's behavior. No API key, server or additional plugin is required by this skill.

## Use

Ask your agent:

> Use the adversarial-engineering skill for this change. Challenge the plan before implementation, review the resulting diff, and verify the acceptance claims. Report finding dispositions and anything you could not verify.

For review only:

> Use adversarial-engineering to review this diff. Do not edit files. Give concrete failure paths and evidence, and distinguish blockers from advisories.

The [English SKILL.md](skills/adversarial-engineering/SKILL.md) is the canonical instruction set. Translated READMEs explain the same workflow and installation; they are not separate skill variants. See [review examples](skills/adversarial-engineering/references/review-examples.md) and [validation scope](docs/VALIDATION.md).

## What makes it different

- Three explicit gates, rather than a single final “looks good.”
- Evidence-backed disagreement: findings can be rejected, but not by confidence alone.
- Honest review provenance: independent review, self-review and missing verification stay distinct.
- Bounded re-review: follow up on changed findings; reopen other checks only when evidence changes.
- Portable instructions: no framework, model vendor or review plugin dependency.

This is a workflow aid, not a guarantee of defect-free code or an automated CI enforcement mechanism. Agent judgment and access to meaningful evidence still matter.

## Contributing and license

See [CONTRIBUTING.md](CONTRIBUTING.md). Original content is licensed under [MIT](LICENSE), copyright CercaTrovato. The compact, installable packaging was inspired by [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills); this is an independent project, without affiliation or endorsement. Its instructions were not copied.

Topics: `agent-skills`, `engineering-management`, `adversarial-review`, `code-review`, `quality-gates`, `verification`, `coding-agents`, `multi-agent`, `claude-code`, `codex`, `cursor`.
