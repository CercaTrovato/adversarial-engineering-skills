# Installation

## Skills CLI

Run from the target project. Node.js/npm and Git must be available. The CLI downloads a third-party package through npm; inspect its source if your organization requires it.

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Choose agents interactively, or append one or more selectors:

| Agent | Selector |
| --- | --- |
| Claude Code | `-a claude-code` |
| Codex | `-a codex` |
| Cursor | `-a cursor` |
| GitHub Copilot | `-a github-copilot` |
| Gemini CLI | `-a gemini-cli` |
| OpenCode | `-a opencode` |
| Cline | `-a cline` |
| Windsurf | `-a windsurf` |
| Roo Code | `-a roo` |
| Continue | `-a continue` |

Add `--copy` to avoid symbolic links (useful on Windows); add `-g` for user scope. These selectors are documented by the [upstream installer](https://github.com/vercel-labs/skills#supported-agents), checked on 2026-10-15. Agent discovery paths and availability may change. No claim of end-to-end testing in every agent is made.

Preview discovery without installing:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --list
```

For a reproducible source, clone a reviewed commit or release and install from its local directory:

```sh
git clone https://github.com/CercaTrovato/adversarial-engineering-skills.git
cd adversarial-engineering-skills
git checkout v1.0.0
```

Then, from your target project, run `npx skills add /path/to/adversarial-engineering-skills --skill adversarial-engineering --copy`, replacing the path with the clone's absolute path. Pin the CLI version too if your environment requires reproducible tooling.

## Manual installation, without Node.js

Download or clone this repository. Copy the entire `skills/adversarial-engineering` folder into your agent's documented project or user skills directory. Preserve `SKILL.md` and `references/` together. For example, Claude Code's project location is `.claude/skills/adversarial-engineering/`; other agents have different discovery paths—consult the upstream matrix and your installed agent's documentation. Do not overwrite an existing skill or project instruction file without inspecting it.

If the agent cannot discover skills, attach `SKILL.md` explicitly to your request and make the referenced example available when needed. This is manual prompt use, not native installation. Reload the agent if necessary, then ask it to identify the skill and explain which gates apply. A successful copy does not prove activation.

## Remove or update

```sh
npx skills remove adversarial-engineering
```

Add `-g` if installed globally. Inspect upstream CLI help for agent-specific removal. For manual installation, remove only the copied `adversarial-engineering` folder after confirming its path. To update, review the new version and rerun the install command; preserve any local customizations first.
