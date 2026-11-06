# Personal website

A single-page personal website (Linktree-style profile card) served by GitHub Pages from the `master` branch at `mariomarroquim.github.io`.

## Project details

This is a personal website, simplified for the mobile era. Much like the Linktree ones. Pushing to `master` deploys it. There is no build step, package manager, linter, or test suite. It's plain static HTML and CSS.

## Conventions

- If the code changes, sync both `AGENTS.md` and `README.md` as well.
- Don't commit and push changes unless explicitly required.
- Before commiting, update both of these in `index.html`:
  - **Copyright year:** the year in the footer (`&copy; YYYY Mário Marroquim`) must be the current year.
  - **Deploy version:** the `<meta name="version">` tag, in the format `YYYY.MM.DD.N`, where `N` counts that day's commit starting at 1.
  - **Asset version:** Add or update `?v=` (query string) with the updated deploy version on any local asset (CSS, image, etc) reference.
  - **Sitemap version:** Update the lastmod tab with the current day in the format `YYYY-MM-DD`.
- This project only uses the `master` branch; commit and push directly to it.
