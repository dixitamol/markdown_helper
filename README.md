# mdview — Markdown Viewer PWA

A zero-dependency, single-file Progressive Web App for reading Markdown files on your phone.

## Features

- **Open `.md` files** from your phone's file system
- **Rendered markdown** — headings, bold, italic, code (inline + blocks), links, lists, blockquotes, horizontal rules, images
- **System theme** — follows your phone's light/dark mode automatically
- **Installable** — add to home screen for native app feel
- **Fully offline** — no network requests, ever
- **Single file** — the entire app is one `index.html`

## Setup

1. Copy `index.html` to your phone (AirDrop, USB, cloud drive, email — whatever)
2. Open it in Chrome (or any Chromium-based browser)
3. Tap the browser menu → **"Add to Home Screen"** / **"Install App"**
4. Launch from your home screen like a regular app

## Usage

1. Tap **Open File**
2. Pick any `.md` file from your phone
3. Read

## Limitations

- Parser covers ~90% of common Markdown (not full GFM spec)
- No tables support in V1
- File access is read-only in V1 (editing comes in V2)
- `showSaveFilePicker` (V2) is Chrome-only on Android

## V2 Roadmap

- [ ] Toggle to raw editor (`<textarea>`)
- [ ] Formatting toolbar (bold, italic, heading, link, list)
- [ ] Save / Save As
- [ ] Live preview toggle
- [ ] Auto-save drafts

## License

MIT — do whatever you want with it.
