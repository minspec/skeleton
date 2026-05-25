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
