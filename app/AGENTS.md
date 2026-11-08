# app/

The full frontend, built with SvelteKit and Tailwind. It is not deployed yet: `plans/app-migration/` covers choosing a host and going live.

## Commands

- `pnpm dev` starts the dev server.
- `pnpm check` type-checks the app.
- `pnpm format` formats the code with Prettier.
- `pnpm format:check` checks formatting without writing.
- `pnpm lint` runs ESLint.
- `pnpm test` runs the Vitest tests.
- `pnpm build` produces a production build.

CI runs `pnpm format:check`, `pnpm lint`, `pnpm check`, `pnpm test` and `pnpm build` whenever `app/` changes.
