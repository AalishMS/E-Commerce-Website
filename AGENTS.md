# AGENTS.md

## What this is

A static, single-page web project (`index.html`). No build tooling, no package manager, no tests. Preview by opening `index.html` in a browser or serving the directory (`npx serve .`).

## Gotchas

- The local folder is named "group SIEP" but the remote is `AalishMS/E-Commerce-Website`. Same project; don't let the mismatch confuse you.
- Content direction is unsettled: the `<title>`/`<h1>` say "E-Commerce Store", but the nav/header say "Explore Patan" (travel/tourism). Ask before writing new copy — don't pick a side on your own.
- All styling is inline in `<head>` using CSS variables in `:root` (palette: `--ink`, `--parchment`, `--maroon`, `--gold`, etc.). Follow that pattern; no external CSS files.
- Fonts come from Google Fonts (Yatra One + Mukta) via a `<link>` tag.

## Git workflow

- Work on feature branches off `main` (currently `home-page-creation`); don't commit directly to `main`.
- Commits are small, lowercase, plain-English ("added welcome message in home page").
- Never force-push; the remote is shared.
