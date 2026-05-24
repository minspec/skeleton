# Codex Instructions for `minspec/skeleton`

## Repository identity

This repository is `minspec/skeleton`.

It is the minimal MinSpec-compatible Symfony project skeleton. Its job is to provide the smallest practical starting point for a MinSpec application while staying close to the Symfony Docker / FrankenPHP / Caddy runtime baseline.

Preserve this repository’s purpose:

- minimal Symfony application shell
- Symfony Docker / FrankenPHP / Caddy runtime baseline
- local development baseline
- no database requirement by default
- no UX stack by default
- no dashboard, workbench, admin panel, demo app, or sample product by default
- higher-level features belong in packages, recipes, adapters, or project-level choices

This repository is not a full starter app, framework distribution, demo application, package workbench, dashboard, or generated application.

## Current naming and terminology

Use only current MinSpec naming, terminology, and repository identity.

Do not use retired project names, retired namespace language, or historical migration framing unless explicitly instructed.

Do not rename MinSpec concepts, invent new package names, or create new doctrine unless explicitly instructed.

## Project doctrine

Preserve MinSpec’s current posture:

- independent and unofficial Symfony-adjacent project
- package-first composition
- Symfony-native terminology
- deterministic install-time wiring
- minimal skeleton first
- AI-aware but not AI-led
- human-reviewed pull-request workflow
- source-of-truth discipline

AI agents may assist with inspection, drafting, and narrowly scoped edits.

AI agents do not own architecture, governance, release authority, repository settings, or source-of-truth decisions.

## Default branch and pull-request workflow

The default branch is `master`.

All changes should be prepared as pull-request-sized working-tree changes.

Do not commit, push, merge, tag, create releases, publish packages, or alter remote settings unless explicitly instructed.

Before editing, report:

1. current branch
2. `git status --short`
3. intended files to change
4. reason each file needs to change

After editing, report:

1. changed files
2. concise diff summary
3. `git status --short`
4. verification performed
5. remaining risks or uncertainty

Do not run `git add` unless explicitly instructed.

## Allowed work by default

For normal maintenance requests, prefer:

- Markdown/docs edits
- README wording fixes
- repository description/tagline text
- source-only metadata review
- small source-only corrections explicitly requested by the user
- comments that clarify existing intent without broadening doctrine

Keep changes small, direct, and reversible.

## Restricted work

Do not modify any of the following unless explicitly instructed:

- application code
- dependency versions
- `composer.lock`
- generated files
- Docker runtime files
- GitHub Actions workflows
- CI configuration
- package metadata
- Packagist/release settings
- branch protection or repository settings
- license files
- security policy files
- CODEOWNERS

Do not add files unless the task clearly requires it.

Do not add demo pages, controllers, UI stacks, database layers, JavaScript tooling, CSS frameworks, dashboards, workbenches, onboarding flows, examples, fixtures, or sample application behavior unless explicitly instructed.

## Dependency and artifact safety

Do not run package installs, dependency updates, generators, Docker builds, runtime commands, or artifact-producing commands unless explicitly instructed.

Do not create or modify local install/build/runtime artifacts.

Do not add generated files to the repository.

If a command may generate files, ask first.

## Command safety

Safe inspection commands:

```bash
git status --short
git branch --show-current
git diff
git diff --stat
find . -maxdepth 3 -type f
grep -R "pattern" .
sed -n '1,200p' file
cat file
```

Do not run unless explicitly instructed:

```bash
composer install
composer update
composer require
npm install
yarn
pnpm
docker build
docker compose up
docker compose build
symfony console
php bin/console
vendor/bin/*
make
```

Do not run broad formatters, code generators, migrations, package installers, dependency updates, Docker builds, or commands that generate local artifacts.

## Editing rules

- Inspect first.
- Make the smallest correct change.
- Preserve existing formatting style.
- Preserve Symfony-native terminology.
- Preserve the minimal skeleton boundary.
- Do not introduce new abstractions, dependencies, package names, or architectural claims.
- Do not silently improve unrelated wording.
- Do not update multiple unrelated files in one task unless explicitly requested.
- If the requested change conflicts with this file, stop and explain the conflict.

## Source-of-truth discipline

Treat this repository as a source-of-truth surface for `minspec/skeleton`, but not for the entire MinSpec ecosystem.

Do not use this repository to define broad MinSpec ecosystem policy unless explicitly instructed.

If a task appears to belong in another repository, say so instead of forcing the change here.

## Response format

For inspection-only tasks:

1. What I inspected
2. Current branch/status
3. Findings
4. Risks or uncertainty
5. Suggested next action

For edit tasks:

1. What I inspected
2. Intended file list
3. Changes made
4. Diff summary
5. Verification performed
6. Remaining risks or uncertainty