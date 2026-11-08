# Move from the teaser to the full app

**Status:** planned

## Goal

Replace the static teaser in `site/` with the SvelteKit app in `app/` on the same custom domain, without taking the teaser down before the app is proven.

## Steps

- [ ] Choose a host and replace `adapter-auto` in `app/` with that host's adapter.
- [ ] Copy the `@theme` block from `site/src/input.css` into `app/src/routes/layout.css`. Any teaser markup you want to keep can be pasted into Svelte components.
- [ ] Deploy `app/` (root directory `app`) and test it on the host's own URL while the teaser stays live.
- [ ] Point the custom domain at the new host. This is the actual switch. To roll back, point it back at GitHub Pages.
- [ ] Once the app is stable, delete `site/` and `.github/workflows/deploy-pages.yml` in one PR, then turn off GitHub Pages in the repo settings.

## Custom domain for the teaser

Add the domain under Settings → Pages and create the DNS records GitHub lists there. No `CNAME` file is needed, and the teaser's links already work at the domain root. Share the custom domain rather than the `github.io` URL, because only the domain can follow the site to its new host.

## Decisions

None yet.
