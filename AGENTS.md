# Personal website

A single-page personal website (Linktree-style profile card) served by GitHub Pages from the `master` branch at `mariomarroquim.github.io`.

## Project details

This is a personal website, simplified for the mobile era. Much like the Linktree ones. Pushing to `master` deploys it. There is no build step, package manager, linter, or test suite. It's plain static HTML and CSS.

## Conventions

- If the code changes, sync both `AGENTS.md` and `README.md` as well.
- Don't commit and push changes unless explicitly required.
- Before commiting, update all these:
  - **Copyright year:** The footer note `&copy; YYYY Mário Marroquim` must contain the current year.
  - **Deploy version:** The header tag `<meta name="version">YYYY.MM.DD.N</meta>` must contain the current day and a count of today's commits.
  - **Asset version:** The `?v=` (add if missing) on any local asset (CSS, image, etc) references must contain the new deploy version.
  - **Sitemap version:** The tag `<lastmod>YYYY-MM-DD</lastmod>` must contain the current day.
- This project only uses the `master` branch; commit and push directly to it.
