# AGENTS.md

## Cursor Cloud specific instructions

This repository is a single-page **static website** for the musician "罗领 / LUOLING". It has no
build step, no package manager, no dependencies, and no test/lint tooling.

- Content lives entirely in `index.html` (inline CSS + one small inline smooth-scroll `<script>`),
  plus assets in `images/` and `CNAME` (custom domain `luolingmusic.cn`).
- Deploy is handled by GitHub Pages via `.github/workflows/pages.yml` on pushes to `gh-pages`
  (the default branch). There is nothing to "build".

### Run it locally (development)

Serve the repo root over HTTP from the project root (do not open `index.html` via `file://`, since
relative asset paths and Google Fonts behave better over HTTP):

```
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. Any Node/Python static server works equally well
(e.g. `npx serve .`); Python's `http.server` is the simplest since Python 3 is preinstalled.

### Notes / gotchas

- The only JS is smooth-scroll for the in-page nav anchors; there is no framework, bundler, or
  hot-reload. Edit `index.html` and refresh the browser to see changes.
- One image asset has a non-ASCII (Chinese) filename; browsers request it URL-encoded and it serves
  fine. Keep both `images/avatar.jpg` and the Chinese-named portrait in sync if replacing.
- The dark grey blocks in the "Works" and "Services" sections are intentional decorative CSS
  backgrounds, not broken images.
- There are no automated tests or linters; validate changes by loading the page in a browser.
