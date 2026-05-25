# MinSpec Skeleton

Minimal Symfony application skeleton for MinSpec projects.

This repository is a Composer/Flex seed. It intentionally does not ship Docker runtime files or a pre-generated Symfony application tree. Composer and Symfony Flex materialize the Symfony application during `composer create-project`.

## Create a project

```bash
composer create-project minspec/skeleton my-app
cd my-app
php bin/console about
```

## Boundary

`minspec/skeleton` owns the minimal Symfony application skeleton.

It does not own:

- Docker Compose files
- Dockerfiles
- Caddy or FrankenPHP runtime configuration
- Docker entrypoints
- first-run Docker bootstrap behavior
Public visibility does not imply public governance, public write access, or an open contribution process. During incubation, source mutation authority remains deliberately restricted to the maintainer and explicitly trusted collaborators.

Pull requests are enabled but restricted to collaborators only. Only users with repository write, maintain, or admin access may open pull requests.

Collaborator PR access is an operational mechanism for trusted maintainers and approved collaborators. It is not a public contribution path.

Issues, security reports, reproducible bug reports, documentation clarity suggestions, and design feedback may be useful where intentionally enabled. Opening an issue or providing feedback does not grant contribution authority, source authority, maintainer status, or approval to submit code changes.

Unsolicited external PRs are not part of the accepted source path during incubation.

AI agents, GitHub Apps, bots, automation, Dependabot, Copilot agents, browser agents, and external tools are not maintainers and do not gain source authority from collaborator-only PR settings.

Those belong in `minspec/docker`.

## Intent

The skeleton should remain small, explicit, and package-first. It should provide a clean Symfony baseline without assuming Doctrine, Twig, AssetMapper, Tailwind, Mercure, Workbench, UI Bundle, Mate tooling, or any application-specific stack.

Additional behavior should be composed later through packages and recipes.

## Expected generated files

After `composer create-project`, Symfony Flex may generate files such as:

- `.env`
- `bin/console`
- `config/`
- `public/`
- `src/`
- `composer.lock`
- `symfony.lock`

Those are generated application files. They are intentionally not committed to this skeleton seed repository.
See [`LICENSE`](LICENSE) for the full license text.
