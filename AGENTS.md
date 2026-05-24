# AGENTS.md

## Purpose

This file defines operating rules for Codex and other local coding agents working inside the `minspec/skeleton` repository.

It is not marketing copy.
It is not a public contribution guide.
It is not a general MinSpec doctrine document.

This file exists to keep agent-assisted work bounded, reviewable, source-controlled, and aligned with the purpose of this package.

Agents may assist the maintainer.
Agents do not decide project direction.

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
- no agent may approve, merge, release, tag, or publish anything
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
- AI may assist development, but AI does not own doctrine, commits, releases, or merge authority.

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

Agents MUST NOT:

- silently broaden task scope
- introduce new doctrine beyond the requested change
- invent package architecture
- add dependencies unless explicitly requested
- remove dependencies unless explicitly requested
- update lock files unless explicitly requested
- generate local build/runtime artifacts unless explicitly requested
- change licensing unless explicitly requested
- alter release, registry, or branch-policy assumptions without explicit instruction
- normalize agent autonomy over human review

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

## Command Policy

Agents may recommend commands, but MUST distinguish recommended commands from commands actually run.

### Low-Risk Inspection Commands

When explicitly asked to inspect, agents may run read-only commands such as:

- `git status --short`
- `git branch --show-current`
- `git diff --stat`
- `git diff`
- `git ls-files`
- `find . -maxdepth 3 -type f`
- `composer validate --strict`, only if Composer is already available and the command will not install or update dependencies

### Commands Requiring Explicit Permission

Agents MUST NOT run these without explicit maintainer permission:

- `composer install`
- `composer update`
- `composer require`
- `composer remove`
- `npm install`
- `yarn`
- `pnpm`
- `docker compose build`
- `docker compose up`
- Symfony console commands that generate files or mutate cache/state
- commands that write to `vendor/`
- commands that write to `node_modules/`
- commands that write to `var/`
- commands that write to `public/build/`
- commands that mutate cache directories
- commands that update lock files
- commands that generate assets or runtime artifacts

If unsure whether a command mutates the repository, do not run it.

## Git Policy

Agents MUST NOT:

- stage files
- commit changes
- push changes
- create branches
- delete branches
- tag releases
- open pull requests
- merge pull requests
- modify remotes
- rewrite history

unless explicitly instructed.

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

Agents MUST NOT claim validation was performed unless it actually was.

Agents MUST NOT claim work is ready for release, Packagist, production, or merge without explicit evidence.

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
- branch, release, registry, or CI settings would be affected
- repository history or naming history would be mentioned
- the task requires guessing project doctrine

When in doubt, preserve the skeleton and ask.

## Agent Response Format

For non-trivial tasks, agents should use this structure.

Before editing:

- `Scope understood`
- `Files likely to change`
- `Commands planned`
- `Risks or ambiguities`

After editing:

- `Files changed`
- `What changed`
- `Validation performed`
- `Validation skipped`
- `Remaining risks`
- `Suggested next step`

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
