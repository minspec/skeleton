---
name: safe-repo-change
description: Make a bounded, source-only MinSpec repository change. Use for small docs/config/source edits after inspection; preserves PR-sized scope, avoids dependency/artifact drift, and reports exact files changed plus verification.
---

# Safe Repo Change

Use this skill when the user asks for a bounded edit inside a MinSpec repository.

This is a Claude Code project skill. It assumes repository doctrine is defined by root `AGENTS.md`, with Claude-specific adaptation in root `CLAUDE.md`.

This skill assumes the repository has already been inspected. If not, run the `inspect-first` workflow before editing.

## Goal

Make the smallest correct change that satisfies the user’s request while preserving MinSpec doctrine, source-of-truth boundaries, and PR hygiene.

## Non-Negotiable Constraints

- Follow root `CLAUDE.md` and root `AGENTS.md`.
- Keep changes PR-sized.
- Modify only files required by the request.
- Prefer source/docs/config edits only.
- Do not install dependencies.
- Do not run package managers.
- Do not update lock files unless explicitly requested.
- Do not run builds, framework commands, Docker builds, or artifact-generating commands unless explicitly requested.
- Do not stage, commit, push, merge, tag, or release unless explicitly requested.
- Do not modify CI/workflow files, branch protections, package metadata, dependency constraints, release config, or security policy unless explicitly requested.
- Do not introduce old retired namespace language.
- Do not create new doctrine when the task only asks for implementation, docs cleanup, or configuration.

## MinSpec Skeleton Boundary

For `minspec/skeleton`, preserve the minimal skeleton purpose:

- minimal Symfony application baseline
- Symfony Docker / FrankenPHP / Caddy runtime baseline
- no database requirement by default
- no default UX/application layer
- no Workbench implementation
- no Mate/MCP implementation
- no package composition beyond the skeleton’s role
- higher-level capabilities should remain install-driven, package-driven, or repo-specific

## Change Workflow

1. Restate the bounded task in one sentence.
2. Confirm the current branch and `git status --short`.
3. Read `CLAUDE.md`, `AGENTS.md`, and all target files before editing.
4. Identify the exact files that will change.
5. Edit only those files.
6. Re-read the changed files.
7. Review the diff.
8. Run only safe, non-generating verification unless the user authorized more.

Safe verification examples:

```bash
git diff --check
git diff --stat
git diff -- <changed-files>
```

Do not run commands that create or mutate local artifacts unless the user explicitly authorized them.

## Required Final Report

After editing, report:

- files changed
- concise summary of what changed
- verification performed
- anything intentionally not changed
- remaining risks or follow-up needed before PR

## Hard Stops

Stop and report instead of editing when:

- another change already exists in a file you need to modify
- the requested edit would expand repository scope
- the task requires generated artifacts
- the task requires dependency, lockfile, CI, release, tag, branch, or package-manager changes without explicit authorization
- the user’s request conflicts with root repository instructions
