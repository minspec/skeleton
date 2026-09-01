# AGENTS.md

This repository is `minspec/skeleton`.

## Repository role

`minspec/skeleton` is the pure Composer/Flex Symfony application skeleton for MinSpec projects.

It is not the Docker runtime repository. Docker Compose, Dockerfiles, server runtime configuration, docker-entrypoint scripts, and first-run Docker bootstrap behavior belong in `minspec/docker`.

## Operating mode: maintainer-directed agent work

Agents work in this repository under the maintainer-directed lane defined in the org `CONTRIBUTING.md` (Maintainer-Directed Agent Work, maintainer decision 2026-09-01):

- The maintainer directs the work and names its scope. Undirected work does not start.
- Agents may branch, commit, push, and open **draft** pull requests through accounts the maintainer granted.
- Every commit carries origin trailers: `Source:` (where the content came from — `original`, a `repo@sha` pointer, a URL, `owner <date>`, or `generated: <tool>`) and `Co-Authored-By:` naming the specific model that did the work, vendor noreply address. Work an agent did not do gets no trailer with its name.
- Author and committer identity remain the maintainer's; agent credit lives in the trailers.
- Agents never approve, merge, ratify, tag, release, publish, or change repository settings, protections, secrets, workflows-permissions, or collaborator access. Ratification is the maintainer's act, always.
- Agents never rewrite history, never force-push, and never delete branches — branches are part of the record.
- Reviews from other agents are welcome: findings go in PR comments; a commit fixing a reviewer's finding may credit the reviewer with a `Reviewed-by:` trailer.

Instruction precedence, when anything conflicts:

1. explicit maintainer instruction for the current task
2. this `AGENTS.md` (with the org `CONTRIBUTING.md` and `GOVERNANCE.md` behind it)
3. tool-specific instruction files (`CLAUDE.md`, `.codex/config.toml`, skills)
4. general model behavior or defaults

Tool-specific files may add stricter rules; they must not weaken this file.

## What this repository holds — and refuses

This repository remains a Composer/Flex seed. Do not add Docker artifacts:

- no `compose.yaml`, `compose.override.yaml`, `compose.prod.yaml`
- no `Dockerfile`, no server runtime configuration, no entrypoint scripts

Do not add generated Symfony application files unless explicitly requested:

- no committed `.env`, `bin/`, `config/`, `public/`, `src/`, `tests/`
- no committed `composer.lock` or `symfony.lock`

Appropriate changes: `composer.json` metadata and constraints, README and documentation, repository policy files, source-control hygiene files, Packagist-facing metadata, MinSpec skeleton doctrine.

## Testing discipline

Do not generate install/build/runtime artifacts inside this repository. To test `composer create-project`, use a scratch directory outside the repository and inspect results there.

## Source and supply-chain policy

Acceptable sources for code patterns: official upstream documentation and repositories, existing code in this repository, approved MinSpec repositories, explicit maintainer-provided instructions. Every commit names its source in a `Source:` trailer; content whose source cannot be named does not go in.

Any change to dependencies, Composer plugins, Docker images, GitHub Actions, external tools, or package metadata is high-risk and requires explicit maintainer approval — supply-chain changes are security-sensitive even when they look routine.

## Secret and credential boundary

Agents must not inspect, print, copy, or rely on secrets or credentials: tokens, auth files, SSH keys, `.env.local` variants, credential-helper output, or the contents of `~/.ssh`, `~/.config/gh`, or other harness credential stores. If a task appears to require a credential the agent does not hold, stop and say so.

## Command discipline

Prefer read-only inspection before editing. Git and `gh` operations inside the lane above are normal work; commands that install dependencies, update lock files, or generate runtime artifacts still require explicit maintainer authorization per task. Permission to run one command does not imply permission for adjacent commands. Never claim a validation ran unless it ran.

## Pull request discipline

Draft-first: a PR opens as a draft and is marked ready only when its checks are green and the maintainer asks. The body states what changed and why, where the content came from (matching the commits' `Source:` trailers), and how it was verified. The maintainer merges; agents do not.

## Hard prohibitions

Agents must not include, revive, or reference retired predecessor namespaces, retired project names, non-MinSpec branding, migration history, old ownership history, unrelated project doctrine, or generic AI hype — and must not make public claims that exceed what this package actually does.

## Naming, wording, and positioning

Use `MinSpec`, `minspec/skeleton`, "minimal Symfony skeleton", "baseline", "starting point". Avoid inflated terms (platform, operating system, universal framework, production-ready application stack).

MinSpec is independent and unofficial. Say "Symfony application skeleton" or "built on Symfony components"; never imply Symfony ownership, endorsement, or official distribution status. Symfony is a trademark of Symfony SAS.

## Dependency and runtime discipline

The skeleton must not accumulate dependencies because they are common in starter templates. No Doctrine, frontend build systems, demo/UX packages, admin bundles, testing frameworks, or AI/MCP tooling by default. Runtime choices live in `minspec/docker`, not here; this file does not name a server runtime.

## Escalation

Stop and ask the maintainer when: the requested change conflicts with this file, would make the skeleton less minimal, or belongs in another package; dependency, lock-file, licensing, CI, release, or settings changes are needed; external source material is required; or the task requires guessing doctrine. When in doubt, preserve the skeleton and ask.

## Operating summary

`minspec/skeleton` is a minimal Symfony skeleton for MinSpec-compatible projects.

Keep it small. Keep it accurate. Keep it source-controlled. Keep it package-specific.

Agents prepare, commit, and submit under the maintainer's direction, with full attribution. The maintainer reviews, ratifies, and merges. Authority does not move.
