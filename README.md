# mdview — Markdown Reader & Editor PWA

A zero-dependency, single-file Progressive Web App for reading and writing Markdown files on your phone.

## Features

- **Open `.md` files** from your phone's file system
- **Rendered markdown** — headings, bold, italic, code (inline + blocks), links, lists, blockquotes, horizontal rules, images, tables (with alignment)
- **Editor mode** — full textarea editor with monospace font and tab support
- **Formatting toolbar** — bold, italic, code, headings, links, lists, tasks, blockquotes, code blocks, tables, horizontal rules
- **Save** — write back to the original file (`showSaveFilePicker`) or download as new file
- **New file** — start writing from scratch without opening anything
- **Keyboard shortcuts** — Ctrl/Cmd+B (bold), Ctrl/Cmd+I (italic), Ctrl/Cmd+S (save)
- **Word & character count** — live stats in editor mode
- **Unsaved changes indicator** — dot next to filename, browser warns before leaving
- **System theme** — follows your phone's light/dark mode automatically
- **Drag & drop** — drop a file onto the page (desktop)
- **Scroll to top** — floating button on long documents
- **Source view** — toggle to see raw markdown
- **Installable** — add to home screen for native app feel
- **Fully offline** — no network requests, ever
- **Single file** — the entire app is one `index.html`

## Setup

1. Copy `index.html` to your phone
2. Open it in Chrome
3. Tap the browser menu → **"Add to Home Screen"** / **"Install App"**
4. Launch from your home screen like a regular app

## Usage

**Reading:** Open File → pick a `.md` → read the rendered output. Toggle "Source" to see raw markdown.

**Writing:** Tap "New File" to start fresh, or open a file then tap "Edit". Use the formatting toolbar or keyboard shortcuts. Tap "Save" when done.

## Limitations

- Parser covers ~90% of common Markdown (not full GFM spec)
- `showSaveFilePicker` (save-in-place) is Chrome-only on Android; other browsers fall back to download
- No image embedding, git integration, or cloud sync

## License

MIT — do whatever you want with it.
