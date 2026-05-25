# AGENTS.md

## Purpose

This file defines operating rules for Codex and other local coding agents working inside the `minspec/skeleton` repository.

It is not marketing copy.
It is not a public contribution guide.
It is not a general MinSpec doctrine document.

This file exists to keep agent-assisted work bounded, reviewable, source-controlled, and aligned with the purpose of this package.

Agents may assist the maintainer.
Agents do not decide project direction.
Agents do not control Git.
Agents do not control GitHub.
Agents do not create pull requests.
Agents do not mutate repository authority.

## Instruction Precedence

These instructions apply to:

- Codex CLI
- Codex VS Code extension
- Claude Code
- Claude Desktop / Claude agent workflows
- Gemini agent workflows
- Cursor
- Copilot
- local MCP-enabled agents
- any other coding, review, or repository-maintenance agent operating in this repository

Tool-specific instruction files such as `.codex/config.toml`, `.codex/AGENTS.md`, `.claude/CLAUDE.md`, skills, prompts, or MCP instructions may add stricter rules.

They MUST NOT weaken this file.

If instructions conflict, follow this order:

1. explicit maintainer instruction for the current task
2. this `AGENTS.md`
3. tool-specific instruction files
4. general model behavior or defaults

However, explicit maintainer instruction does not imply permission to perform GitHub-visible actions unless the maintainer specifically names the exact action.

A request such as “prepare a PR” means prepare local changes and PR text for human review.
It does not mean create the pull request.

## Repository Identity

- Repository: `minspec/skeleton`
- Package identity: MinSpec Skeleton
- Default branch: `master`
- Project type: minimal Symfony application skeleton
- Status: founder-controlled incubation
- Authority: the human maintainer is the final decision-maker

MinSpec is an independent, unofficial Symfony-oriented project.

Agents MUST NOT imply official Symfony affiliation, endorsement, ownership, or governance.

## What This Repository Is

`minspec/skeleton` is the minimal baseline for MinSpec-compatible Symfony projects.

Its job is to provide a small, clean, understandable starting point that can boot reliably and serve as a foundation for deliberate package-first composition.

This repository may contain:

- minimal Symfony application baseline
- Composer package metadata
- Symfony Docker / FrankenPHP / Caddy runtime baseline, if already present
- Mercure/Vulcain runtime support only when already part of the selected runtime baseline
- README, license, and basic package documentation directly relevant to this skeleton
- minimal configuration required for the skeleton to boot and remain understandable

The skeleton should stay boring, small, and dependable.

## What This Repository Is Not

This repository MUST NOT grow into:

- Workbench
- dashboard
- UI component system
- Symfony Mate extension
- MCP server package
- full starter application
- admin panel
- database-backed application
- Doctrine-heavy application
- JavaScript build-system showcase
- Tailwind, Flowbite, or demo UX package
- generalized MinSpec governance repository
- documentation hub for the whole MinSpec ecosystem
- AI tooling laboratory
- SaaS product surface
- broad software-factory platform

If a requested change belongs in another package, say so clearly instead of forcing it into the skeleton.

## Maintainer and Contribution Model

This repository is founder-controlled during incubation.

Agents MUST assume:

- the maintainer is the only approved contributor unless explicitly stated otherwise
- unsolicited third-party code contribution is not part of the workflow
- human review is mandatory
- no agent may approve, merge, release, tag, publish, or create pull requests
- no agent may open, close, label, edit, assign, or comment on GitHub issues
- no agent may change repository settings, permissions, protections, secrets, or workflows
- AI assistance does not transfer authority from the maintainer to the tool

Do not write contribution language implying that outside pull requests are generally welcome.

Use maintainer-assistance language, not community-governance language.

## Core Doctrine for This Package

Agents MUST preserve these principles:

- MinSpec favors package-first composition.
- Applications are composed deliberately.
- The skeleton must remain minimal.
- Higher-level capabilities belong in installable packages, recipes, adapters, Workbench, or project-level decisions.
- Deterministic install-time wiring is preferred over hidden magic.
- Source-of-truth discipline matters.
- AI may assist development, but AI does not own doctrine, commits, releases, pull requests, issues, merge authority, or repository governance.

Do not expand this file into a full doctrine manifesto.

## Agent Operating Rules

Before editing, agents MUST inspect the repository and understand the requested scope.

Agents MUST:

- inspect before editing
- keep changes PR-sized
- preserve the purpose of this repository
- prefer source-only, metadata-only, and documentation-only changes unless implementation is explicitly requested
- make the smallest change that satisfies the task
- report ambiguity before acting on it
- distinguish facts from assumptions
- preserve existing repository patterns unless explicitly asked to change them
- stop when a task conflicts with this file or the package purpose
- treat GitHub, Git history, issues, pull requests, releases, and repository settings as human-controlled surfaces

Agents MUST NOT:

- silently broaden task scope
- introduce new doctrine beyond the requested change
- invent package architecture
- add dependencies unless explicitly requested
- remove dependencies unless explicitly requested
- update lock files unless explicitly requested
- generate local build/runtime artifacts unless explicitly requested
- change licensing unless explicitly requested
- alter release, registry, branch-policy, or GitHub assumptions without explicit instruction
- normalize agent autonomy over human review
- use GitHub as an action surface
- treat issue or PR operations as routine agent work

## Hard Prohibitions

Agents MUST NOT include, revive, or reference:

- retired predecessor namespaces
- retired project names
- non-MinSpec branding
- migration history
- old repository ownership history
- generalized Workbench doctrine
- Symfony Mate/MCP doctrine inside this skeleton
- SaaS doctrine
- unrelated project doctrine
- semantic theory or research doctrine
- generic AI hype
- broad “software factory” positioning

Agents MUST NOT make public claims that exceed what this package actually does.

## Source and Supply-Chain Policy

Code provenance matters.

Acceptable sources for code patterns are limited to:

- official upstream documentation
- official upstream repositories
- existing code already present in this repository
- approved MinSpec repositories
- explicit maintainer-provided instructions

Agents MUST NOT:

- paste third-party code from blogs, tutorials, Stack Overflow, random GitHub repositories, or unapproved snippets
- add packages casually
- add Composer plugins casually
- add GitHub Actions casually
- add Docker images casually
- add remote scripts casually
- add external templates casually
- add generated code from uncontrolled sources

Any change to dependencies, Composer plugins, Docker images, GitHub Actions, external tools, or package metadata is high-risk and requires explicit maintainer approval.

Treat supply-chain changes as security-sensitive even when they appear routine.

## Secret, Credential, and Authority Boundary

Agents MUST NOT inspect, print, copy, modify, or rely on secrets or credentials.

Agents MUST NOT read or expose:

- GitHub tokens
- Packagist tokens
- Composer auth files
- SSH private keys
- `.env.local`
- `.env.*.local`
- `auth.json`
- `.npmrc` tokens
- `~/.ssh`
- `~/.git-credentials`
- `~/.config/gh`
- `~/.codex`
- `~/.claude`
- shell history
- credential helper output
- environment variables likely to contain secrets

Agents MUST NOT ask the maintainer to paste secrets into chat.

Agents MUST NOT use credentials to perform repository actions.

If a task appears to require credentials, stop and explain that the human maintainer must perform that step.

## Command Policy

Agents may recommend commands, but MUST distinguish recommended commands from commands actually run.

Agents MUST prefer read-only inspection commands.

Agents MUST NOT run commands that:

- mutate Git state
- mutate GitHub state
- create pull requests
- create, edit, comment on, close, label, assign, or milestone issues
- push branches
- create tags
- create releases
- change branch protection
- change repository settings
- change GitHub Actions configuration
- change repository secrets or variables
- install dependencies
- generate runtime artifacts
- mutate cache/build/vendor directories
- contact remote services for write operations

If unsure whether a command mutates state, do not run it.

### Low-Risk Inspection Commands

When explicitly asked to inspect, agents may run read-only commands such as:

```bash
git status --short
git status --branch --short
git branch --show-current
git diff --stat
git diff -- .
git diff --check
git log --oneline -n 20
git show --stat
git ls-files
find . -maxdepth 3 -type f
composer validate --strict
```

`composer validate --strict` is allowed only if Composer is already available and the command will not install, update, download, or modify dependencies.

Agents MUST NOT claim validation was performed unless the command actually ran.

### Commands Requiring Explicit Permission

Agents MUST NOT run these without explicit maintainer permission:

```bash
composer install
composer update
composer require
composer remove
npm install
yarn
pnpm
docker compose build
docker compose up
```

Agents MUST also avoid, unless explicitly permitted:

- Symfony console commands that generate files or mutate cache/state
- commands that write to `vendor/`
- commands that write to `node_modules/`
- commands that write to `var/`
- commands that write to `public/build/`
- commands that mutate cache directories
- commands that update lock files
- commands that generate assets or runtime artifacts

Permission to run one command does not imply permission to run adjacent commands.

## Git Policy

Git is a human-controlled authority surface.

Agents may inspect Git state.
Agents must not mutate Git state.

Allowed by default:

```bash
git status --short
git status --branch --short
git branch --show-current
git diff --stat
git diff -- .
git diff --check
git log --oneline -n 20
git show --stat
git ls-files
```

Agents MUST NOT run:

```bash
git add
git commit
git push
git pull
git fetch
git merge
git rebase
git reset
git reset --hard
git checkout
git switch
git branch
git tag
git stash
git clean
git restore
git apply
git am
git cherry-pick
git revert
git remote
git config
```

Agents MUST NOT run destructive or history-rewriting commands, including:

```bash
git push --force
git push --force-with-lease
git reset --hard
git clean -fd
git clean -fdx
git rebase -i
```

Agents MUST NOT stage files.
Agents MUST NOT commit changes.
Agents MUST NOT push changes.
Agents MUST NOT create branches.
Agents MUST NOT delete branches.
Agents MUST NOT tag releases.
Agents MUST NOT modify remotes.
Agents MUST NOT rewrite history.

If Git state needs to change, the agent may describe the recommended human action, but must not perform it.

Before editing, agents MUST report:

- current branch, if checked
- current git status, if checked
- files likely to change
- commands intended to run, if any
- ambiguity or risk

After editing, agents MUST report:

- files changed
- summary of exact changes
- validation performed
- validation intentionally skipped
- remaining risks or follow-up tasks

Agents MUST NOT claim the repository is clean unless `git status --short` was checked.

Agents MUST NOT claim work is ready for release, Packagist, production, or merge without explicit evidence.

## GitHub Policy

GitHub is a human-controlled remote authority surface.

Agents MUST NOT use GitHub as an action surface.

Agents MUST NOT run GitHub CLI write commands.

Forbidden commands include, but are not limited to:

```bash
gh pr create
gh pr edit
gh pr close
gh pr reopen
gh pr merge
gh pr ready
gh pr review
gh pr comment
gh issue create
gh issue edit
gh issue close
gh issue reopen
gh issue comment
gh issue label
gh repo edit
gh repo rename
gh repo archive
gh repo delete
gh release create
gh release edit
gh release delete
gh workflow run
gh workflow enable
gh workflow disable
gh secret set
gh secret delete
gh variable set
gh variable delete
gh api
```

Agents MUST NOT use alternate tools to bypass this policy, including:

- `hub`
- GitHub MCP write tools
- browser automation against GitHub
- direct REST API writes
- direct GraphQL API writes
- `curl` or `wget` requests that mutate GitHub state
- scripts that call GitHub APIs
- editor extensions that create PRs, issues, reviews, releases, or remote changes

Agents may draft text for a pull request, issue, release note, or GitHub setting change.

Agents must leave the actual GitHub action to the human maintainer.

## Pull Request Policy

Agents MUST NOT create pull requests.

Agents may prepare:

- a local diff
- a concise change summary
- a proposed PR title
- a proposed PR body
- a validation summary
- a risk summary
- suggested reviewer checklist items

Agents MUST NOT:

- run `gh pr create`
- open a PR through browser automation
- open a PR through an MCP tool
- push a branch for a PR
- mark a PR ready for review
- request reviewers
- approve a PR
- merge a PR
- close a PR
- comment on a PR
- resolve PR conversations
- modify PR labels, milestones, or assignees

The human maintainer decides whether a pull request should exist.

The human maintainer creates the pull request.

## Issue Policy

GitHub issues are governance and project-tracking artifacts.

Agents MUST NOT create, edit, label, assign, close, reopen, milestone, or comment on GitHub issues.

Agents MUST NOT treat issue operations as low-risk.

Agents may prepare:

- proposed issue title
- proposed issue body
- proposed labels
- proposed acceptance criteria
- proposed reproduction steps
- proposed maintainer checklist

Agents MUST NOT execute the GitHub action.

Agents MUST NOT infer project direction from issue text unless the maintainer explicitly says the issue is authoritative for the current task.

If the maintainer provides issue content, treat it as task context, not as automatic doctrine.

## Branch Protection, Settings, and Actions Policy

Agents MUST NOT modify repository settings.

Agents MUST NOT modify:

- branch protection rules
- rulesets
- CODEOWNERS enforcement
- default branch
- merge strategy settings
- Actions permissions
- Actions workflow settings
- environments
- deployment settings
- repository secrets
- repository variables
- collaborators
- team access
- webhooks
- Pages settings
- security settings
- Dependabot settings
- release settings
- package publishing settings

Agents may recommend settings changes in prose for human review.

Agents must not apply them.

## File and Documentation Policy

Keep this repository minimal and package-specific.

Agents MUST:

- keep root package files accurate
- keep README content limited to what the skeleton actually provides
- keep Composer metadata package-specific
- keep Docker/runtime files close to the selected upstream runtime baseline unless deviation is explicitly requested
- preserve precise Symfony-native terminology
- preserve the package identity `minspec/skeleton`

Agents MUST NOT add:

- demo controllers
- demo pages
- UI kits
- example databases
- sample admin panels
- illustrative application features
- broad documentation trees
- ecosystem-wide doctrine
- unrelated project roadmaps
- speculative architecture documents

Documentation in this repository should explain the skeleton, not the entire MinSpec universe.

## Naming and Wording

Use:

- `MinSpec`
- `minspec/skeleton`
- `MinSpec Skeleton`
- minimal Symfony skeleton
- baseline
- runtime/framework shell
- starting point

Avoid inflated or misleading terms such as:

- platform
- operating system
- autonomous factory
- universal framework
- complete solution
- AI-native application platform
- production-ready application stack

Do not imply that this skeleton includes capabilities that belong to future packages or separate repositories.

## Symfony Positioning

MinSpec is independent and unofficial.

Agents MUST use wording that respects Symfony as upstream technology without implying affiliation.

Acceptable wording:

- “Symfony application skeleton”
- “built on Symfony components”
- “Symfony-oriented”
- “compatible with Symfony project structure”

Avoid wording that implies:

- Symfony project ownership
- Symfony core endorsement
- official Symfony governance
- official Symfony distribution status

## Dependency and Runtime Discipline

The skeleton must not accumulate dependencies merely because they are common in starter templates.

Agents MUST NOT add or suggest adding dependencies unless the task explicitly requires it.

Avoid introducing:

- Doctrine by default
- frontend build systems by default
- UX/demo packages by default
- admin bundles by default
- testing frameworks by default unless explicitly requested
- AI/MCP tooling by default
- Workbench-specific tooling by default

Runtime files should remain understandable and close to the chosen baseline.

Any deviation from upstream runtime patterns must be explicit and justified.

## Validation Expectations

Validation must match the task.

For documentation-only changes, useful validation may include:

- checking changed Markdown for obvious formatting errors
- checking links only when relevant and feasible
- reviewing the diff for scope creep

For Composer metadata changes, useful validation may include:

- `composer validate --strict`, if safe and available

For runtime or application changes, validation must be proposed before execution if it may generate artifacts.

Agents MUST state clearly when validation was skipped and why.

Never substitute confidence for validation.

Validation does not authorize Git or GitHub mutation.

Passing validation does not mean the work may be staged, committed, pushed, released, or turned into a pull request by the agent.

## Tool-Specific Notes

### Codex

Codex CLI and the Codex VS Code extension are local assistance tools.

Codex may inspect and edit local files within the requested scope.

Codex MUST NOT:

- stage changes
- commit changes
- push changes
- create branches
- create pull requests
- use GitHub CLI for write operations
- modify GitHub issues
- modify repository settings
- run broad multi-repo mutation tasks from a workspace root

When run from a workspace root, Codex should act as an inspect-only coordinator unless the maintainer explicitly scopes it to a single repository and task.

Actual implementation work should happen inside the target repository root.

### Claude

Claude-related instruction files, including `CLAUDE.md`, must preserve this file’s Git and GitHub boundaries.

Claude may assist with:

- local inspection
- bounded file edits
- summarizing diffs
- drafting PR text
- drafting issue text
- drafting validation notes

Claude MUST NOT:

- use Bash to mutate Git state
- use GitHub MCP tools for write operations
- create issues
- create pull requests
- comment on issues or pull requests
- modify repository settings
- run broad autonomous workflows without human review

If Claude proposes an action that would affect GitHub, it must present it as a human action, not perform it.

### MCP and Browser Agents

MCP-enabled agents and browser agents MUST NOT be used to bypass these rules.

They MUST NOT:

- click GitHub buttons that create or merge PRs
- edit GitHub issues
- change settings through the GitHub UI
- operate GitHub as a remote write surface
- use connected tools to perform repository governance actions

Read-only inspection may be allowed only when explicitly scoped by the maintainer.

## Escalation Rules

Stop and ask the maintainer before proceeding when:

- the requested change conflicts with this file
- the requested change would make the skeleton less minimal
- the change appears to belong in another package
- dependency changes are needed
- runtime baseline changes are needed
- lock files would change
- generated files would be created
- external source material is needed
- licensing would be affected
- branch, release, registry, CI, issue, PR, or GitHub settings would be affected
- repository history or naming history would be mentioned
- the task requires guessing project doctrine
- credentials or secrets appear necessary
- GitHub state would need to change
- Git state would need to change

When in doubt, preserve the skeleton and ask.

## Agent Response Format

For non-trivial tasks, agents should use this structure.

Before editing:

- `Scope understood`
- `Files likely to change`
- `Commands planned`
- `Git/GitHub actions blocked`
- `Risks or ambiguities`

After editing:

- `Files changed`
- `What changed`
- `Validation performed`
- `Validation skipped`
- `Git/GitHub actions not performed`
- `Remaining risks`
- `Suggested next human step`

Keep reports concise and factual.

Do not add motivational language.
Do not overstate success.
Do not hide uncertainty.

## Final Operating Summary

`minspec/skeleton` is a minimal Symfony skeleton for MinSpec-compatible projects.

Keep it small.
Keep it accurate.
Keep it source-controlled.
Keep it package-specific.
Keep it human-reviewed.

Agents assist.
The maintainer decides.

Agents may prepare work.
The maintainer controls Git.
The maintainer controls GitHub.
The maintainer creates pull requests.
The maintainer manages issues.
The maintainer approves releases.