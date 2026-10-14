# Validation scope

Release candidate: 1.0.0. Validation date: 2026-10-15.

This document separates package checks from behavioral evidence.

## Checks performed

- Skill Creator structural validator: passed using Python UTF-8 mode. This checks skill structure, not engineering judgment.
- Markdown relative links: all resolved across 14 Markdown files. Eight localized README pages were inspected for workflow and authorization consistency; no native-speaker review is claimed.
- Skills CLI 1.7.2: local copy installation succeeded in an isolated Windows workspace for the ten agent selectors documented in INSTALL.md. The CLI mapped these to five physical directories; both shipped skill files matched the source by SHA-256. This verifies packaging and installer routing, not activation inside ten applications.
- Independent package review found an ambiguity that would block self-review even when local policy did not require independence. The wording was corrected and a focused independent re-review closed that finding.
- One independent scenario exercise used a synthetic catalog change plus a single passing list test. The reviewer identified unfiltered detail and saved-item reads, blocked acceptance, and explicitly declined to claim runtime verification. This scenario resembles the included example; it is illustrative evidence, not an unbiased benchmark or broad effectiveness measurement.
- Public installation and version-tag discovery are checked as a release step after publication; local installation alone does not establish remote availability.

## Reproduce

From an empty disposable project directory with Git and Node.js/npm, run:

```sh
npx skills@1.7.2 add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering -a claude-code -a codex -a cursor -a github-copilot -a gemini-cli -a opencode -a cline -a windsurf -a roo -a continue --copy -y
```

Inspect the copied SKILL.md and references against the release source. To evaluate behavior, use a separate agent with a realistic request and raw artifacts; record findings, evidence limits, and whether the task was actually completed. Do not infer agent activation from a successful installer exit.

Limits: no claim of defect prevention, universal agent activation, native-speaker translation review, production deployment validation or CI enforcement. The translated pages are localized introductions; the English skill is canonical.
