# open-ui

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

## Custom domain for the teaser

Add the domain under Settings → Pages and create the DNS records GitHub lists there. No `CNAME` file is needed, and the teaser's links already work at the domain root. Share the custom domain rather than the `github.io` URL, because only the domain can follow the site to its new host.

## Moving to the full app

1. Choose a host and replace `adapter-auto` in `app/` with that host's adapter.
2. Copy the `@theme` block from `site/src/input.css` into `app/src/routes/layout.css`. Any teaser markup you want to keep can be pasted into Svelte components.
3. Deploy `app/` (root directory `app`) and test it on the host's own URL while the teaser stays live.
4. Point the custom domain at the new host. This is the actual switch. To roll back, point it back at GitHub Pages.
5. Once the app is stable, delete `site/` and `.github/workflows/deploy-pages.yml` in one PR, then turn off GitHub Pages in the repo settings.

## License

Copyright (c) 2026 The open-ui Contributors.

open-ui is licensed under the [GNU Affero General Public License v3.0 or later](LICENSE) (`AGPL-3.0-or-later`).
