# open-ui

This repository is archived. Make changes in [openpickleball/frontend](https://github.com/openpickleball/frontend) instead.

| Folder   | What it is                                  | Guide                                |
| -------- | ------------------------------------------- | ------------------------------------ |
| `site/`  | Static teaser, live on GitHub Pages         | [site/AGENTS.md](site/AGENTS.md)     |
| `app/`   | Full SvelteKit frontend, not deployed yet   | [app/AGENTS.md](app/AGENTS.md)       |
| `plans/` | Plans for multi-PR units of work            | [plans/AGENTS.md](plans/AGENTS.md)   |

`site/` and `app/` are independent projects with separate dependencies and lockfiles. There is no root `package.json`, so run `pnpm` from inside the project you're changing.

## Conventions

- Use Node 26 (`.nvmrc`) and pnpm.
- Keep `tailwindcss` on the same exact version in `site/` and `app/` until the teaser is removed.
- Before starting multi-step work, check `plans/` for an existing plan.
