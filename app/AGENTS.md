# app/

The full frontend, built with SvelteKit and Tailwind. It is not deployed yet: `plans/app-migration/` covers choosing a host and going live.

## Commands

- `pnpm dev` starts the dev server.
- `pnpm check` type-checks the app.
- `pnpm build` produces a production build.

CI runs `pnpm check` and `pnpm build` whenever `app/` changes.
