# Mathla — CAPS Maths Tutor
A single-file, zero-build-process web app for CAPS maths practice (grades 10-12). Choose your subject and grade, practice by topic, sit past-paper style question sets, and track your progress by topic.
See it in action here

## What it does
- Choose between Maths and Mathematical Literacy for grades 10-12
- Practice by topic (questions banks, automatically marked) (`BANK` in `script.js`)
- Sit past-paper style practice papers (printable) (`REAL_PAPERS` in `script.js`
- Track your progress (questions answered, accuracy by topic) (`mathla_stats_v1` in `localStorage`)
- Toggle light/dark mode (`data-theme` on ``)
- 6 languages supported (English, Afrikaans, Setswana, Sepedi, isiZulu, Xitsonga) (switcher in app, uses a `I18N` object and `data-i18n`/`data-i18n-html` attributes)

All in your browser - no server/database/API needed.

## The files

```

mathla/

├── index.html # markup + and tags

├── styles.css # styles + print media queries

├── script.js # everything else

└── README.md # this file

```

The three files should be kept in the same directory - `index.html` references them both via relative paths:

```html

...

```

## To try it out

If you have the files on your computer, you can simply double-click `index.html` to open it in your browser. Alternatively, you can serve the files from a local server, so that relative paths and any potential API calls in the future work properly:

```bash

cd mathla

python3 -m http.server 8000

# then open http://localhost:8000 in a browser

```

## To make changes

| I want to... | I'll edit... |

|----------------------------------------|-------------------------------------------------------------|
| Change colors, layout, fonts, etc. | `styles.css` - main colors are in `:root` and `html[data-theme="light"]` |
| Add practice questions | the `BANK` object in `script.js` |
| Add past papers | the `REAL_PAPERS` object in `script.js` |
| Change copy or language support | the `I18N` object in `script.js`, and the `data-i18n`/`data-i18n-html` attributes in `index.html` |
| Edit the page layout or copy | `index.html` |
| Delete all progress (for testing) | delete `mathla_stats_v1` in `localStorage` (via devtools) |
To add a new language:
- Add a new key/value pair to the `I18N` object in `script.js`. The keys should match those in the `en` object
- Add an `isiXhosa` (or similar) to the `` in `index.html`
The theming is controlled by CSS variables in `:root` (dark mode) and `html[data-theme="light"]` (light mode) in `styles.css`. To change the colors, edit those variables.

## Browser support
Straight HTML/CSS/JS with `localStorage`, CSS variables and `window.print()` - so it should work in any modern browser. No API calls or databases.

## Notes
- Progress is saved in the browser's localStorage - it is not shared or stored anywhere, and will be deleted if the user clears their browser data.
- The print view for practice papers uses some CSS `@media print` queries to hide extra UI elements.
