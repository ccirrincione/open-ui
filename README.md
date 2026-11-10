# open-ui

> [!IMPORTANT]
> **This repository is archived.** Its teaser, SvelteKit app, plans and agent tooling moved to [openpickleball/frontend](https://github.com/openpickleball/frontend), which serves www.openpb.org. Open issues and pull requests there.

| Folder  | What it is                                         | Status                       |
| ------- | -------------------------------------------------- | ---------------------------- |
| `site/` | One-page teaser: static HTML + Tailwind CLI        | Live on GitHub Pages for now |
| `app/`  | Full frontend: SvelteKit + Tailwind, needs a server | In development, not deployed |

The two are independent projects, each with its own dependencies and lockfile. Work in `app/` never affects the live teaser. Both use Node 26 (`.nvmrc`) and pnpm.

## Teaser (`site/`)

```bash
cd site
pnpm install
pnpm dev
```

`pnpm dev` rebuilds the CSS as you edit. Open `site/public/index.html` in a browser to view the page. Only `site/public/` is published.

Pushing changes under `site/` to `main` deploys the teaser through `.github/workflows/deploy-pages.yml`. PRs run the build only.

## App (`app/`)

```bash
cd app
pnpm install
pnpm dev
```

`.github/workflows/ci-app.yml` type-checks and builds the app whenever `app/` changes. It never deploys.

Keep `tailwindcss` on the same exact version in both projects until the teaser is removed.

## Plans

Larger units of work live in [`plans/`](plans/AGENTS.md), including the [move from the teaser to the full app](plans/app-migration/plan.md).

## License

Copyright (c) 2026 The open-ui Contributors.

open-ui is licensed under the [GNU Affero General Public License v3.0 or later](LICENSE) (`AGPL-3.0-or-later`).
