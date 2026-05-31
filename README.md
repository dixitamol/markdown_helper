# mdview

A fast, fully offline markdown reader and editor that lives in a single HTML file. No install, no dependencies, no server — just open it in a browser.

**Live:** [https://\<your-username\>.github.io/mdview/](https://github.com)

---

## Overview

mdview was built around one constraint: everything in one `.html` file. No npm, no bundler, no CDN calls, no cookies, no tracking. The markdown parser is hand-rolled; the editor is a styled `<textarea>` with keyboard shortcut wiring. It works fully offline once the file is loaded.

The target use case is reading and lightly editing `.md` files on any device — particularly useful on mobile or locked-down machines where installing tools isn't an option.

---

## Features

### Reader
- Rendered markdown with clean typography (Georgia serif body, system-ui UI elements)
- Full dark mode via `prefers-color-scheme` — no toggle needed
- Drag-and-drop `.md` files directly onto the page
- Scroll-to-top button (appears after 400px scroll)
- HTML export — renders the current file to a self-contained `.html`
- Print stylesheet with clean layout and href expansion on links
- Fullscreen mode via the browser Fullscreen API

### Editor
- Live preview toggle (Edit ↔ Preview ↔ Source)
- Format toolbar: Bold, Italic, Inline code, H1–H3, Link, Bullet list, Ordered list, Task list, Blockquote, Code block, HR, Table insert
- Undo / Redo via `execCommand`
- Auto-continue lists and blockquotes on `Enter`; break out of them with a second `Enter` on an empty item
- Tab key inserts 2-space indent
- Adjustable editor font size (A+ / A−)
- Unsaved-changes dot indicator in the toolbar
- `beforeunload` warning if you try to navigate away with unsaved changes

### Find & Replace
- In-editor find with match count and prev/next navigation
- Case-insensitive replace one / replace all
- Keyboard: `Ctrl+F` to open, `Enter`/`Shift+Enter` to step, `Escape` to close

### Save
- Uses the **File System Access API** (`showSaveFilePicker`) where available — saves back to the original file in place
- Falls back to a browser download on unsupported browsers (Safari, Firefox ESR)

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/⌘ + B` | Bold |
| `Ctrl/⌘ + I` | Italic |
| `Ctrl/⌘ + S` | Save |
| `Ctrl/⌘ + F` | Find |
| `Ctrl/⌘ + H` | Find & Replace (focus replace field) |

### Markdown Support

| Feature | Notes |
|---------|-------|
| Headings | H1–H6 |
| Bold, italic, bold+italic | `**`, `*`, `***` and `__` variants |
| Strikethrough | `~~text~~` |
| Inline code | `` `code` `` |
| Fenced code blocks | ` ``` lang ` with language class |
| Blockquotes | Nested supported |
| Unordered lists | `-`, `*`, `+`, nested |
| Ordered lists | `1.` with auto-increment |
| Task lists | `- [ ]` / `- [x]` |
| Tables | GFM-style with left/center/right alignment |
| Links | `[text](url)` — open in new tab |
| Images | `![alt](src)` |
| Footnotes | `[^id]` references + definitions |
| Horizontal rules | `---`, `***`, `___` |
| Inline HTML | Safe passthrough: `br hr details summary mark kbd abbr sup sub small u ins del` |
| Hard line breaks | `\n` inside paragraphs → `<br>` |
| `<mark>` highlight | Renders with yellow background |
| `<kbd>` keys | Styled keyboard key rendering |
| `<details>`/`<summary>` | Collapsible sections |

---

## Usage

```
# Open a file
→ Click "Open File" or drag a .md file onto the window

# Create a new file
→ Click "New File" — opens in edit mode with a blank document

# Switch modes
→ Edit   : toggles between rendered preview and textarea editor
→ Source : shows the raw markdown source (read-only view)

# Save
→ Ctrl+S or the Save button in edit mode
→ Uses File System Access API if available; falls back to download

# Export
→ "HTML" button in view mode → standalone rendered HTML file
```

---

## Deployment

The app is deployed as a static file on **GitHub Pages**.

### Setup (one-time)

```bash
git init
git add index.html
git commit -m "init"
git branch -M main
git remote add origin https://github.com/<username>/mdview.git
git push -u origin main
```

Then: **Settings → Pages → Deploy from branch → `main` / `root`**

### Updates

```bash
git add index.html && git commit -m "vX.X.X: description" && git push
```

Auto-deploys in ~60 seconds. No build step required.

---

## Changelog

### v2.1.2 — GitHub Pages Process
- Confirmed single-file deployment on GitHub Pages
- No configuration required (`index.html` at repo root is sufficient)
- Documented deployment workflow in README

### v2.1.1 — Icon & Branding
- Added inline SVG favicon (base64-encoded data URI in `<head>`)
  - Design: `#` hash mark on a blue rounded square — zero external asset
  - Works at all browser favicon sizes (16px → 64px)
  - No external icon files; everything remains self-contained
- Added landing page app icon (80×80 inline SVG with gradient)
  - CSS `drop-shadow` filter with dark mode adaptation
- Added `<meta name="description">` for SEO / link previews

### v2.1 — Editor Fixes & Polish
- Fixed auto-continue for task lists (preserves `[ ]` prefix on new line)
- Fixed ordered list break-out on empty item (removes prefix, continues prose)
- Fixed blockquote auto-continue and break-out behaviour
- Undo/Redo wired to `execCommand` (reliable cross-browser history)
- Find & Replace: `Enter`/`Shift+Enter` to step through matches
- Find & Replace: replace-all now case-insensitive
- `Ctrl+H` shortcut focuses replace field directly
- Word/character count visible in status bar during edit mode
- Unsaved-changes dot indicator added to toolbar
- `beforeunload` guard prevents accidental navigation with unsaved work
- Export HTML button hidden during edit mode (only shown in view mode)

### v2.0 — Editing Mode
- Added full editing mode with `<textarea>`-based editor
- Sticky format toolbar with all major markdown constructs
- Auto-continue behaviour for lists and blockquotes on `Enter`
- Tab key inserts 2-space indent (no focus trap)
- Save via File System Access API with download fallback
- HTML export of rendered content to standalone file
- Adjustable editor font size (A+ / A−)
- Find & Replace panel (in-editor, not browser find)
- Raw source view mode (read-only, monospace)
- Status bar with live word and character count
- "New File" button on landing creates an empty document in edit mode

### v1.1 — Tables & UX
- Full GFM table support with left/center/right column alignment
- Toolbar back button (←) to return to the landing page
- `showSaveFilePicker` integration (File System Access API) with download fallback
- Footnote support: `[^id]` inline refs + `[^id]: definition` rendering
- Scroll-to-top button (appears after 400px of scroll)
- Drop overlay visual feedback on drag-enter
- Filename shown in toolbar and document `<title>` on file open
- Fullscreen toggle button
- Print stylesheet: clean layout, href expansion, toolbar hidden
- Mobile polish: `touch-action`, overflow scroll, larger tap targets

### v1.0 — Initial Release
- Single-file markdown reader — open `.md`, `.markdown`, `.txt` files
- Hand-rolled markdown parser (no external library)
  - Headings, bold, italic, bold+italic, strikethrough
  - Inline code and fenced code blocks with language class
  - Blockquotes, unordered/ordered/nested lists, task lists
  - Inline images and links (open in new tab)
  - Horizontal rules, inline HTML passthrough (safe tag allowlist)
- Dark mode via `prefers-color-scheme`
- Drag-and-drop file loading
- Mobile-first responsive layout
- Zero dependencies, zero network requests, fully offline

---

## Known Issues

| Issue | Severity | Notes |
|-------|----------|-------|
| **File System Access API unavailable on Firefox & Safari** | Low | Falls back to download silently. Saving re-downloads the file rather than updating in place. No data loss. |
| **`execCommand` undo deprecated in some browsers** | Low | Still functional in all major browsers as of 2025, but the API is on a deprecation path. Will need to be replaced with a manual undo stack in a future version. |
| **Nested blockquotes lose inner `>` on re-edit** | Low | Parser renders them correctly; the raw source is preserved and round-trips safely. Visual only. |
| **Table cells with line breaks (`<br>`) not supported** | Low | GFM tables don't support multi-line cells natively; neither does this parser. Workaround: use HTML passthrough directly. |
| **Large files (>500KB) may cause input lag on mobile** | Low | The textarea re-renders on every `input` event. No virtualisation is in place. Rare in practice for typical `.md` files. |
| **`apple-touch-icon` not set** | Cosmetic | iOS "Add to Home Screen" uses a viewport screenshot rather than the SVG icon. Fixing requires a raster PNG, which would break the single-file constraint. |
| **Find & Replace only active in edit mode** | By design | View-mode find uses the browser's native Ctrl+F. This may be surprising the first time. |

---

## Future Prospects

### Near-term (incremental improvements)

- **Manual undo/redo stack** — replace `execCommand` with a proper history ring buffer, giving reliable multi-level undo in all browsers
- **Split-pane preview** — side-by-side editor and rendered view on wide viewports (≥1024px)
- **Local storage persistence** — auto-save draft to `localStorage` so work survives an accidental tab close
- **Syntax highlighting** — lightweight token-based highlighting in code blocks (no external library; inline tokeniser)
- **Word wrap toggle** — option to disable wrapping in the editor for wide tables or code-heavy files
- **Custom theme** — persist a user-selected accent colour via `localStorage`

### Medium-term (meaningful scope)

- **Outline / TOC panel** — collapsible heading tree in a sidebar, generated from the parsed document, with scroll-spy
- **Multi-file tabs** — open several files simultaneously without navigating back to the landing screen
- **Image paste** — paste from clipboard → encode as base64 data URI and insert as an `![img]()` reference, keeping the file self-contained
- **Vim keybindings** — optional mode switchable from a settings panel
- **Search within rendered view** — highlight search terms in the preview pane, not just the editor

### Longer-term (architectural)

- **PWA / Service Worker** — cache the app shell so it loads without a network connection even as a remote URL, not just a local file
- **Collaborative editing** — WebRTC-based peer sync using CRDTs (no server required); highly experimental
- **Plugin API** — expose parser hooks so custom renderers (e.g. Mermaid diagrams, LaTeX math via KaTeX) can be added without forking the file
- **OPFS backend** — use the Origin Private File System API for persistent, sandboxed file storage in the browser with no download required

---

## Project Structure

```
mdview/
└── index.html      # The entire application — HTML + CSS + JS in one file
```

That's it.

---

## Design Principles

1. **Single file, always.** Every asset — styles, scripts, icons, fonts — lives inside `index.html`. A user can save the page once and use it forever with no connection.
2. **No dependencies.** No npm, no bundler, no CDN. The markdown parser is ~250 lines of vanilla JS.
3. **Progressive enhancement.** Core reading works in any browser. The File System Access API and Fullscreen API are used where available and gracefully degrade.
4. **Offline first.** The app makes zero network requests after the initial page load.
5. **Readable source.** The HTML file is unminified. Anyone can open it in a text editor and understand what it does.

---

## License

MIT — do whatever you want with it.
