@AGENTS.md

# Claude Code Adapter for MinSpec Skeleton

This file intentionally imports `AGENTS.md` as the repository source of truth.

Do not duplicate, reinterpret, or weaken the root agent doctrine here. This file exists only to adapt Claude Code behavior to the repository’s existing agent instructions.

## Claude Code Role

Claude Code may help inspect, plan, review, and make bounded repository changes when explicitly requested.

Treat this repository as the minimal MinSpec skeleton. Preserve its role as a clean Symfony runtime baseline, not a full application starter, package composition layer, Workbench implementation, or Mate/MCP implementation.

## Instruction Precedence

Use this precedence order:

1. System, safety, and platform instructions.
2. Root `AGENTS.md`.
3. This `CLAUDE.md` adapter.
4. The current user request.
5. Claude auto memory or prior conversation context.

If any instruction conflicts with root `AGENTS.md`, stop and surface the conflict instead of guessing.

Claude auto memory is useful context, not repository authority. If memory contradicts files in this repository, trust the repository.

## Required Operating Pattern

Before making nontrivial changes:

1. Inspect the repository state.
2. Read `AGENTS.md`.
3. Read the files directly relevant to the task.
4. Check the current branch and working tree state.
5. Identify the exact files that may change.
6. Keep the change PR-sized.

Do not edit first and explain later.

## Repository Safety Rules

Do not run package installs, Composer updates, Symfony commands, Docker builds, build commands, test commands, asset compilation, generators, or artifact-producing commands unless the user explicitly authorizes them for the current task.

Do not stage, commit, push, merge, tag, release, or alter branch protection unless the user explicitly requests that action.

Do not modify dependencies, lock files, CI workflows, release configuration, package metadata, Docker/runtime configuration, or security-sensitive files unless explicitly requested.

Do not introduce generated files, local cache files, IDE artifacts, build outputs, or dependency directories into the repository.

If existing uncommitted changes appear in files you would touch, stop and report them before editing.

## MinSpec Skeleton Boundary

Preserve this repository as a minimal skeleton.

Do not add by default:

- database requirements
- default application UX
- dashboard UI
- Workbench implementation
- Mate/MCP implementation
- package composition machinery
- recipe behavior that belongs in a recipes repository
- broad framework doctrine that belongs in organization-level docs

Higher-level capabilities should remain install-driven, package-driven, or repository-specific unless the user explicitly asks to add them here.

## Branch and PR Discipline

MinSpec repositories may use `master`. Do not assume `main`.

Confirm the current branch before branch-sensitive guidance.

Prepare changes for pull request review. Do not treat local edits as final merged work.

When finishing a change, report:

- files changed
- what changed
- verification performed
- verification intentionally skipped
- risks or follow-up needed
- suggested PR title and summary when useful

## Language and Doctrine Hygiene

Use current MinSpec terminology only.

Do not revive old retired namespace language. If old retired namespace language is found in the repository, flag it as a cleanup issue rather than repeating it casually.

Do not invent new doctrine while performing maintenance. If a requested change seems to require new doctrine, surface that as a decision point.

## Claude-Specific Behavior

Use concise plans for multi-step work.

Prefer file reads, diffs, and source inspection over execution.

Prefer narrow edits over broad rewrites.

Do not rely on hidden assumptions. If repository state is unknown, inspect it.

If asked to perform a review, return a severity-ordered finding list and a clear verdict.

If asked to make a change, make only the requested change and report the exact diff-relevant outcome.