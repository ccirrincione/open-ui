# site/

One-page teaser built with static HTML and the Tailwind CLI. It is temporary: `plans/app-migration/` ends with deleting this folder.

- `public/` is the only folder that gets published.
- `src/input.css` compiles to `public/assets/css/main.css`. The output is generated, so edit the input.

## Commands

- `pnpm dev` rebuilds the CSS on change. Open `public/index.html` in a browser to view the page.
- `pnpm build` produces the minified CSS.

## Deployment

Merging changes under `site/` to `main` deploys the teaser to production. PRs run the build only.
