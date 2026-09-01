---
name: inspect-first
description: Inspect-first workflow for MinSpec repositories before planning or editing. Use when asked to inspect, review, diagnose, understand, or prepare changes; enforces git status awareness, source-only inspection, and no installs/builds/generated artifacts unless explicitly authorized.
---

# Inspect First

Use this skill before modifying any MinSpec repository, and whenever the user asks to inspect, review, diagnose, understand, plan, or prepare a change.

This is a Claude Code project skill. It adapts the MinSpec inspect-first workflow for Claude while deferring repository doctrine to the root `AGENTS.md` and `CLAUDE.md` files.

## Purpose

Build a grounded view of the repository before acting. Do not infer repository state from memory, prior chats, package names, or assumptions. The repository on disk is the source of truth.

## Operating Rules

- Read root `CLAUDE.md` and root `AGENTS.md` before making or recommending repository changes.
- Treat the current repository contents, current branch, and working tree state as authoritative.
- Prefer read-only inspection commands and file reads.
- Do not install packages.
- Do not run Composer updates.
- Do not run Symfony commands.
- Do not run Docker builds.
- Do not generate local artifacts.
- Do not stage, commit, or push outside a task the maintainer directed (see AGENTS.md, maintainer-directed lane). Never merge, tag, or release.
- Do not create broad refactors when the user asked for a bounded change.
- Do not revive old retired namespace language. If encountered, flag it as a cleanup issue.

## Required Inspection

When shell access is available, gather the equivalent of:

```bash
pwd
git status --short
git branch --show-current
git log -1 --oneline
```

Then inspect the relevant project files, usually including:

- `CLAUDE.md`
- `AGENTS.md`
- `README.md`
- `composer.json`
- any files directly named by the user
- any files likely to be touched by the requested change

If shell access is unavailable, read the equivalent files and state what could not be verified.

## Repository Boundary Check

For `minspec/skeleton`, preserve the repository’s role as a minimal Symfony runtime skeleton.

Do not add, imply, or scaffold higher-level product layers unless explicitly requested, including:

- database requirements
- default UX stack
- dashboard/application UI
- Workbench implementation
- Mate/MCP implementation
- package composition beyond the skeleton boundary
- install-time recipe behavior that belongs in a recipes repository

## Before Editing

Before changing files, produce a compact inspection summary:

1. Current branch and working tree state.
2. Instruction files read.
3. Files likely to be edited.
4. Guardrails that apply.
5. Any blockers, ambiguity, or uncommitted user changes that could be overwritten.

Proceed only when the change is safely bounded by the user’s request and repository instructions.

## Hard Stops

Stop and report instead of editing when:

- the repository cannot be identified confidently
- `CLAUDE.md` or `AGENTS.md` is missing or unreadable
- the requested edit conflicts with repository doctrine
- the working tree has existing changes in files you would touch
- the task requires dependency, lockfile, CI, workflow, branch-protection, release, or package-metadata changes not explicitly authorized
- completing the request would require generated artifacts or local build/install side effects
