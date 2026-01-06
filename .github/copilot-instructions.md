# Copilot / AI agent instructions (project-specific)

Purpose: Quickly orient AI coding agents to be productive in this repository.

Big picture
- This repository is a small static website: the root `index.html` is the app, and `images/` contains the media assets. See [index.html](index.html) and [README.md](README.md).
- No backend, build system, package manifest, or tests are present — most changes are edits to static HTML/CSS and image assets.

Key files and patterns
- Main shell: [index.html](index.html). Layout, content and image references live here.
- Assets: the `images/` directory stores all photos used by the page. Image `src` values are relative (e.g. `./images/box 1.jpg`).
- Text is UTF-8 and includes Ukrainian strings — preserve encoding and diacritics when modifying files.

Developer workflows (what you'll actually do)
- Preview locally: open `index.html` in a browser, or run a simple static server from the project root:

  - `python -m http.server 8000`
  - or `npx http-server` (if Node tooling is available)

- Debugging: use browser DevTools to inspect layout and network for missing image paths. When images do not load, check for spaces/special characters in filenames (see Image notes below).

Project-specific conventions & gotchas
- Image filenames contain spaces (e.g. `box 1.jpg`, `img-1.jpg`). Prefer converting spaces to `-` when adding new images, and update `src` accordingly to avoid URL-encoding issues.
- Keep paths relative and use `./images/` in `index.html` (existing pages do this). Do not introduce absolute paths.
- There is no build step — any generated CSS/JS must be committed as plain files and referenced from `index.html`.

Integration points & external dependencies
- None were discovered: no package.json, no server code, and no CI config. Assume isolated, static-host deployment (GitHub Pages or any static host).

If updating or merging an existing Copilot instructions file
- Preserve any existing sections titled "Big picture", "Workflows", or "Conventions" and merge project-specific bullets above under those headings.

Examples (concrete edits you might be asked to make)
- Add or rename an image: place `new-image.jpg` in `images/`, update `index.html` image tag to `<img src="./images/new-image.jpg" alt="...">`.
- Local preview: run `python -m http.server 8000` and visit `http://localhost:8000`.
- Fix broken image: check `index.html` for `./images/box 1.jpg` and either rename the asset or update the `src` to match the file name exactly.

Questions for the maintainer
- Do you want image filenames normalized (no spaces) and a short naming convention for new assets?

Please review — I can iterate on tone, level of detail, or include additional commands (e.g., linting, CI) if you add those files.
