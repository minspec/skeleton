---
name: pr-review
description: Review MinSpec repository changes before a PR or merge. Use to inspect working-tree diffs, catch doctrine drift, generated artifacts, dependency mutations, branch mistakes, oversized changes, and old retired namespace language.
---

# PR Review

Use this skill to review repository changes before opening, updating, or merging a pull request.

This skill reviews and reports. It does not approve, stage, commit, push, merge, tag, or release.

## Goal

Identify whether the current changes are safe, bounded, doctrine-aligned, and ready for human review.

## Read-Only Review Commands

When shell access is available, inspect with read-only commands such as:

```bash
git status --short
git branch --show-current
git diff --name-only
git diff --stat
git diff --check
git diff
```

If reviewing a branch against a base branch, first confirm the actual base branch. Do not assume `main`; MinSpec repositories may use `master`.

## Review Lenses

Check for:

### Scope Control

- Is the change PR-sized?
- Does it modify only files needed for the stated task?
- Does it avoid unrelated formatting churn?
- Does it avoid broad rewrites when a targeted fix was requested?

### Source and Artifact Hygiene

Flag unexpected changes to:

- `vendor/`
- `node_modules/`
- `var/`
- build output
- cache output
- generated assets
- local IDE files
- package-manager artifacts
- lock files unless explicitly authorized

### Dependency and Runtime Drift

Flag unexpected changes to:

- `composer.json`
- `composer.lock`
- Docker files
- Symfony runtime config
- package constraints
- install scripts
- CI/workflow files
- release/tag metadata

### MinSpec Doctrine

Confirm the change preserves:

- independent/unofficial Symfony project posture
- package-first composition
- Symfony-native terminology
- minimal skeleton boundaries
- recipes as deterministic install-time wiring when recipes are discussed
- AI-aware but not AI-led framing
- no old retired namespace language

### Skeleton Boundary

For `minspec/skeleton`, flag any unrequested addition of:

- database requirements
- default UX stack
- dashboard/application UI
- Workbench implementation
- Mate/MCP implementation
- install-time recipe logic
- broad package composition concerns

### PR Safety

Check whether the change is suitable for a pull request:

- clear title and summary possible
- risks identified
- verification is sufficient for the change type
- no direct-to-default-branch assumptions
- no hidden generated files
- no unreviewed external code or pasted snippets
- no unexplained source-of-truth divergence

## Required Output

Produce:

1. **Verdict**: `PASS`, `NEEDS FIX`, or `BLOCKER`.
2. **Changed files**: grouped by purpose.
3. **Findings**: severity-ordered, with file paths.
4. **Doctrine check**: pass/fail notes.
5. **Artifact/dependency check**: pass/fail notes.
6. **Verification performed**.
7. **Recommended next action**.
8. **Draft PR title and summary** if the change is ready or close to ready.

## Severity Definitions

- `BLOCKER`: must fix before PR or merge.
- `HIGH`: likely doctrine, security, source-of-truth, branch, dependency, or artifact risk.
- `MEDIUM`: scope, maintainability, unclear wording, or verification gap.
- `LOW`: polish or optional cleanup.

## Hard Stops

Do not approve or recommend merge if:

- generated artifacts are included unexpectedly
- dependency/lock/runtime/CI changes are unrequested
- old retired namespace language appears
- repository scope has expanded without authorization
- branch/base assumptions are unclear
- source authority is unclear
- the diff cannot be inspected
