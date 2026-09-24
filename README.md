# Mathla — CAPS Maths Tutor Landing Page

Landing page for Mathla, a CAPS-aligned maths practice tool for Grades 10–12.

## Files

- `index.html` — page markup, links the two files below
- `styles.css` — all styles (theme variables, layout, components)
- `script.js` — all behavior (theme toggle, language switch, quiz/paper modals, etc.)

Originally one file; split so each part can be edited on its own. They're linked via:

```html
<link rel="stylesheet" href="styles.css">
...
<script src="script.js"></script>
```

Keep all three files in the same folder — the links are relative paths.

## Running it

No build step. Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server
```

## Notes

- Light/dark theme via `data-theme` attribute + CSS variables in `:root`.
- Multi-language text uses `data-i18n` / `data-i18n-html` attributes on elements; translations are wired up in `script.js`.
- Print styles for the practice-paper modal are in `styles.css` under `@media print`.
