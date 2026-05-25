# MinSpec Skeleton

Minimal MinSpec project skeleton built on the `dunglas/symfony-docker` runtime baseline.

This repository provides the smallest practical starting point for a MinSpec-compatible application:

- Symfony core application baseline
- FrankenPHP + Caddy runtime via Symfony Docker
- local HTTPS-ready development environment
- Mercure and Vulcain runtime support
- no database requirement
- no UX layer by default
- install-driven growth for higher-level capabilities

---

## Purpose

`minspec/skeleton` is intended to be the canonical starting point for new MinSpec-compatible Symfony projects.

It is intentionally minimal.

The goal is to establish a clean baseline that:

- boots reliably
- runs in Docker immediately
- stays close to upstream Symfony Docker
- avoids preloading unnecessary application concerns
- leaves higher-order capabilities to installable packages, recipes, adapters, or project-level decisions

This is not a full starter app.

This is the base runtime and framework shell.

---

## What is Included

### Symfony baseline

A minimal Symfony application with only the framework-level pieces required to boot and run.

### Symfony Docker runtime

This skeleton uses [`dunglas/symfony-docker`](https://github.com/dunglas/symfony-docker) as its canonical runtime baseline:

- FrankenPHP
- Caddy
- local HTTPS
- development bind mounts
- production-oriented container structure

### Mercure and Vulcain runtime support

Mercure and Vulcain remain part of the runtime layer because they fit naturally into the FrankenPHP/Caddy stack.

That does not mean every MinSpec application must use them at the application level.

They are available as runtime capabilities.

---

## What is Not Included

The base skeleton intentionally does not include:

- Doctrine / database configuration
- Twig
- AssetMapper
- Stimulus
- Turbo
- Live Components
- Tailwind
- Security/auth scaffolding
- Messenger
- Symfony Mercure bundle integration
- dashboard/admin UI
- domain-specific application code

These should be added intentionally through packages, recipes, adapters, or project-level decisions.

---

## Philosophy

MinSpec favors a constraint-driven, composition-first architecture.

The skeleton should contain only what is required to establish the canonical runtime and framework baseline.

Everything else should be added deliberately.

In practical terms:

- the skeleton defines the baseline
- Symfony Docker defines the runtime
- packages define capabilities
- recipes define wiring
- MinSpec doctrine defines the guardrails

---

## Getting Started

### 1. Create a new project

```bash
composer create-project minspec/skeleton my-app
cd my-app
```

Until `minspec/skeleton` is available through Packagist, use the Git repository or a local Composer path repository.

### 2. Start Docker

```bash
docker compose build --pull
docker compose up --wait
```

### 3. Open the app

```text
https://localhost
```

If your system already has something bound to port `80` or `443` locally, stop that service or adjust the published ports in `compose.yaml`.

---

## Development Workflow

The development environment uses `compose.override.yaml`, which:

- builds the development image locally
- bind-mounts the project into `/app`
- enables hot reload/watch behavior
- runs the app in `dev` mode

Typical workflow:

```bash
docker compose up --wait
```

Then edit your files locally as normal.

---

## Runtime Notes

### No database by default

This skeleton does not assume persistence.

If your project needs a database, add it later through the appropriate package, recipe, adapter, or project-level decision.

### Mercure and Vulcain

Mercure and Vulcain are present at the runtime level because they are part of the modern Symfony Docker / FrankenPHP / Caddy stack.

Application-level usage remains optional.

### HTTPS

Local HTTPS is supported through the Caddy/FrankenPHP runtime.

Depending on your local trust configuration, you may see certificate warnings in some clients during development.

---

## Project Scope

This repository is responsible for:

- minimal Symfony project structure
- canonical Docker runtime baseline
- clean local development experience
- stable foundation for installable MinSpec capabilities

This repository is not responsible for:

- providing a full application starter
- shipping all common bundles by default
- defining business/domain architecture
- forcing UI or persistence assumptions into every project
- accepting unsolicited code mutation during incubation

---

## Suggested Next Steps

After bootstrapping a new project from this skeleton, install only the capabilities you actually need.

Examples might include:

- UI/runtime packages
- user/auth packages
- API packages
- Doctrine/persistence packages
- async/realtime integrations
- project-specific bundles
- MinSpec adapters or guardrail packages

The skeleton should remain small.

The application should grow intentionally.

---

## Repository Structure

```text
.
├── compose.yaml
├── compose.override.yaml
├── Dockerfile
├── frankenphp/
├── config/
├── public/
├── src/
├── bin/
└── tests/
```

Key files:

- `compose.yaml` — base runtime definition
- `compose.override.yaml` — development workflow and local bind mounts
- `Dockerfile` — FrankenPHP-based multi-stage image build
- `frankenphp/Caddyfile` — Caddy/FrankenPHP runtime configuration

---

## Upstream Runtime Basis

This project intentionally stays close to:

- [`dunglas/symfony-docker`](https://github.com/dunglas/symfony-docker)
- [`dunglas/frankenphp`](https://github.com/dunglas/frankenphp)

The goal is to benefit from a modern Symfony runtime without reinventing the container/runtime layer.

MinSpec focuses on application architecture, package boundaries, and AI-safe development guardrails above that baseline.

---

## Repository Posture

This repository is public for visibility, review, reproducible feedback, and source-of-truth development.

Public visibility does not imply public governance, public write access, or an open contribution process. During incubation, source mutation authority remains deliberately restricted to the maintainer and explicitly trusted collaborators.

Pull requests are enabled but restricted to collaborators only. Only users with repository write, maintain, or admin access may open pull requests.

Collaborator PR access is an operational mechanism for trusted maintainers and approved collaborators. It is not a public contribution path.

Issues, security reports, reproducible bug reports, documentation clarity suggestions, and design feedback may be useful where intentionally enabled. Opening an issue or providing feedback does not grant contribution authority, source authority, maintainer status, or approval to submit code changes.

Unsolicited external PRs are not part of the accepted source path during incubation.

AI agents, GitHub Apps, bots, automation, Dependabot, Copilot agents, browser agents, and external tools are not maintainers and do not gain source authority from collaborator-only PR settings.

---

## Status

This repository is an actively shaped baseline for MinSpec application bootstrapping.

It is intentionally strict, minimal, and designed to evolve through installable capabilities rather than by inflating the base skeleton.

---

## License

MinSpec Skeleton is licensed under the Apache License, Version 2.0.

See [`LICENSE`](LICENSE) for the full license text.
