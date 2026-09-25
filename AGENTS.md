# AGENTS.md

Single-page static web app (no build step, no package.json, no tests, no lint). UI text and README are in **Indonesian** — write new UI copy in Indonesian.

## Layout
- `index.html` — the entire app: HTML structure, custom CSS (`<style>`), and all JS at the end of `<body>`. There is no separate JS/CSS file.
- `bg.png` — body background, referenced by CSS at `index.html:16`. Do not remove.

## Gotchas
- README claims "Tailwind CSS", but the app uses hand-written CSS classes (`.card`, `.btn-yellow`, `.field-group`, etc.). Do not introduce Tailwind.
- Deploy = `git push origin main`; GitHub Pages serves the repo root. No CI, no build, no separate deploy step. Verify locally by opening `index.html` in a browser (or `python3 -m http.server`).
- Form handling is inline `onclick`/`onchange` attributes wired to functions in the inline script (e.g. `addFormField`, `generatePrompt`, `togglePercentageInput`). Keep selectors (`#cpl-container .field-group` etc.) in sync with the static HTML they parse.