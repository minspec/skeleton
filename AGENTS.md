# AGENTS.md

This repository is `minspec/skeleton`.

## Repository role

`minspec/skeleton` is the pure Composer/Flex Symfony application skeleton for MinSpec projects.

It is not the Docker runtime repository. Docker Compose, Dockerfiles, Caddy/FrankenPHP configuration, docker-entrypoint scripts, and first-run Docker bootstrap behavior belong in `minspec/docker`.

## Hard boundaries

Do not add Docker artifacts to this repository:

- no `compose.yaml`
- no `compose.override.yaml`
- no `compose.prod.yaml`
- no `Dockerfile`
- no `Caddyfile`
- no `frankenphp/`
- no Docker entrypoint scripts

Do not add generated Symfony application files to this repository unless explicitly requested:

- no committed `.env`
- no committed `bin/`
- no committed `config/`
- no committed `public/`
- no committed `src/`
- no committed `tests/`
- no committed `composer.lock`
- no committed `symfony.lock`

This repository should remain a Composer/Flex seed.

## Allowed work

Appropriate changes include:

- `composer.json` metadata and dependency constraints
- README / documentation
- repository policy files
- source-control hygiene files
- Packagist-facing metadata
- MinSpec skeleton doctrine

## Testing discipline

Do not generate local install/build/runtime artifacts inside this repository while making source edits.

To test `composer create-project`, use a scratch directory outside the repository, for example:

```bash
mkdir -p ~/projects/_scratch
cd ~/projects/_scratch
rm -rf minspec-skeleton-test
composer create-project minspec/skeleton minspec-skeleton-test --prefer-dist
```

Inspect results there, not inside this repository.

## Source-of-truth discipline

Make changes through pull requests. Keep changes small and reviewable.

Before proposing edits, classify the file or behavior as one of:

- Composer/Flex skeleton seed
- generated Symfony application output
- Docker/runtime bootstrap
- repository governance/docs

Only modify the layer that owns the behavior.
