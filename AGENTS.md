# Personal website

A single-page personal website (Linktree-style profile card) served by GitHub Pages from the `master` branch at `mariomarroquim.github.io`.

## Project details

- `index.html`: the whole page: avatar, name, title, social links list, and contact buttons (WhatsApp, email), plus a footer copyright line.
- `css/custom.css`: all custom styling (gradient background, Bebas Neue heading font, link list, button widths). It overrides Bootstrap.
- `img/avatar.jpg`: used both as the profile photo and as the favicon.

External dependencies come from CDNs, with nothing vendored:
- Bootstrap 4.5.2 CSS (with an SRI `integrity` hash, so if you change the version you must update the hash too)
- Google Fonts (Bebas Neue)
- Font Awesome kit script (icons use `fab fa-*` / `far fa-*` classes)

## Conventions

- If the code changes, sync both `AGENTS.md` and `README.md` as well.
- Don't commit and push changes unless explicitly required.
- This project only uses the `master` branch; commit and push directly to it.
