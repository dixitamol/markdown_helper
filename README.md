# mdview — Markdown Reader & Editor PWA

A zero-dependency, single-file Progressive Web App for reading and writing Markdown files on your phone.

## Features

### Reader
- **Rendered markdown** — headings, bold, italic, code, links, lists (nested), blockquotes, horizontal rules, images, tables (with alignment), footnotes, task lists
- **HTML passthrough** — safe tags: `<details>`, `<summary>`, `<mark>`, `<kbd>`, `<abbr>`, `<sup>`, `<sub>`, and more
- **Source view** — toggle to see raw markdown
- **System theme** — follows your phone's light/dark mode automatically
- **Export to HTML** — download rendered output as a standalone `.html` file
- **Print-friendly** — clean output with URL annotations on links

### Editor
- **Full textarea editor** with monospace font and tab support
- **Formatting toolbar** — bold, italic, code, H1–H3, link, lists, tasks, blockquotes, code blocks, tables, HR
- **Auto-continue lists** — Enter after a list item automatically adds the next bullet/number; empty Enter exits the list
- **Find & replace** — search with match count, next/prev navigation, replace one or all
- **Undo/redo buttons** — essential for mobile where Ctrl+Z isn't available
- **Font size control** — A-/A+ buttons to adjust editor text size
- **Save** — write back to the original file (`showSaveFilePicker`) or download as new file
- **New file** — start writing from scratch
- **Keyboard shortcuts** — Ctrl/Cmd+B, I, S, F, H
- **Word & character count** — live stats in editor mode
- **Unsaved changes indicator** — dot next to filename, browser warns before leaving

### General
- **Drag & drop** — drop a file onto the page (desktop)
- **Scroll to top** — floating button on long documents
- **Fullscreen mode** — distraction-free reading/writing
- **Installable** — add to home screen for native app feel
- **Fully offline** — no network requests, ever
- **Single file** — the entire app is one `index.html`

## Setup

1. Copy `index.html` to your phone
2. Open it in Chrome
3. Browser menu → **"Add to Home Screen"** / **"Install App"**

## Limitations

- Parser covers ~90% of common Markdown (not full GFM spec)
- No syntax highlighting in code blocks
- `showSaveFilePicker` (save-in-place) is Chrome-only on Android; others fall back to download
- No image embedding, git integration, or cloud sync

## License

MIT — do whatever you want with it.
