# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **single-page static website** — a bilingual (Chinese/English)
portfolio for the musician 罗领 / LUOLING. There is no build system, package manager,
test suite, or linter.

Structure:
- `index.html` — the entire site (HTML + inlined CSS + a small inline JS smooth-scroll script for `nav a[href^="#"]`).
- `images/` — image assets (note: one file, `罗领-黑白西装形象照.jpg`, has a non-ASCII/Chinese filename).
- `CNAME` — custom domain (`luolingmusic.cn`) used by GitHub Pages.
- `.github/workflows/pages.yml` — deploys the repo root (`path: '.'`) to GitHub Pages on every push to the `gh-pages` branch. There is **no build step**; files are uploaded as-is.

Development / running:
- Serve the site locally from the repo root with any static file server, e.g. `python3 -m http.server 8000`, then open `http://localhost:8000/`. There is nothing to install or compile.
- Because the site is static, there is no dev "hot reload" — refresh the browser after editing `index.html`.

Lint / test / build:
- None exist. There is no lint, test, or build command. Validation is manual: serve the file and check it renders in a browser.

Deploy:
- The `gh-pages` branch is the deploy branch (this is the working/default branch). Pushing to it triggers the GitHub Pages workflow.
