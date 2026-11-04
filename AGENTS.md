# Personal website

A single-page personal website (Linktree-style profile card) served by GitHub Pages from the `master` branch at `mariomarroquim.github.io`.

## Project details

- `index.html`: the whole page: avatar, name, title, social links list, and contact buttons (WhatsApp, email), plus a footer copyright line. The `<head>` holds the SEO metadata: description, robots, canonical URL, Open Graph, Twitter card, and JSON-LD `Person` data. These use absolute `https://mariomarroquim.github.io/` URLs, so keep them in sync if the title, description, avatar, or social links change.
- `css/custom.css`: all custom styling. It overrides Bootstrap and covers:
  - the gradient background, with drifting color blobs in the fixed `.backdrop` layer
  - the Bebas Neue heading font
  - the rotating avatar ring
  - the staggered `.reveal` entrance (each element's `--i` sets its order)
  - the frosted-glass link cards and raised 3D contact buttons

  Animations only move or fade elements (`transform` and `opacity`), which keeps them smooth on phones. Hover effects only apply on devices with a mouse or trackpad (`@media (hover: hover)`). All motion is turned off under `prefers-reduced-motion`.
- `img/avatar.jpg`: the profile photo, and the source of the icons in `img/` (`favicon-32.png`, `apple-touch-icon.png` at 180px for iOS, `icon-192.png` and `icon-512.png` for Android). If the avatar changes, regenerate them at those sizes.
- `img/qrcode.svg`: a static QR code for `https://mariomarroquim.github.io/`, shown below the contact buttons. It was generated with the Python `segno` library (error correction M, 4-module quiet zone). Regenerate it if the site URL changes.
- `manifest.webmanifest`: the web app manifest for Android "Add to Home screen" (name, colors, icons).
- Mobile: the viewport uses `viewport-fit=cover`, so `body` pads itself with `env(safe-area-inset-*)` to stay clear of notches. Links and buttons are at least 44px tall for touch.
- `robots.txt` and `sitemap.xml`: let all crawlers in and list the single page URL. Update the sitemap's `<lastmod>` date when the page content changes.

External dependencies come from CDNs, with nothing vendored:
- Bootstrap 5.3.8 CSS from jsDelivr (with an SRI `integrity` hash, so if you change the version you must update the hash too)
- Google Fonts (Bebas Neue)
- Font Awesome kit script (icons use `fab fa-*` / `far fa-*` classes)

## Conventions

- If the code changes, sync both `AGENTS.md` and `README.md` as well.
- Don't commit and push changes unless explicitly required.
- This project only uses the `master` branch; commit and push directly to it.
- On every deploy (every push to `master`), update both of these in `index.html`:
  - **Copyright year:** the year in the footer (`&copy; YYYY Mário Marroquim`) must be the current year.
  - **Deploy version:** the `<meta name="version">` tag, in the format `YYYY.MM.DD.N`, where `N` counts that day's deploys starting at 1. Its value is repeated in a `?v=` query string on every local CSS, image, and manifest URL. Replace every occurrence (for example, find and replace the old value) so the URLs change and browsers fetch fresh files instead of cached ones. Add `?v=` with the current value to any new local asset reference.
