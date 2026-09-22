# My Notes

A fast, local-first notes app with GitHub sync, folders, tags, rich text
formatting, and a modern glass/neon UI — split into a proper multi-file
project.

## Structure

```
notes-app/
├── index.html      # markup
├── css/
│   └── style.css   # design system + all styling
├── js/
│   └── app.js       # app logic (storage, GitHub sync, editor, UI)
└── README.md
```

## Running it

No build step — it's plain HTML/CSS/JS. Just open `index.html` in a
browser, or serve the folder locally:

```bash
# from inside notes-app/
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly by double-clicking also works fine.

## Features

- **Local-first storage** — notes persist to `localStorage`, with an
  in-memory fallback if storage is unavailable.
- **Folders & tags** — nested folders, color-coded tags, live search.
- **Multi-note tabs** — work on several notes at once.
- **Rich text editor** — bold/italic/underline, font size, text & highlight
  color, alignment, tab handling.
- **GitHub sync** — push/pull notes as JSON to a GitHub repo, with
  auto-push every 5 seconds while editing and auto-pull on load.
- **Import/export** — load/save a JSON snapshot, drag-and-drop import of
  plain text files.
- **Command palette** — `⌘K` / `Ctrl+K` to fuzzy-jump to any note.
- **Live stats** — word count, character count, and estimated read time
  update as you type.
- **Dynamic UI** — ambient particle background, staggered list animations,
  crossfade on note switch, magnetic cursor glow on interactive elements.
- **Responsive** — dedicated mobile layout with a bottom tab bar.

## Notes on the GitHub sync token

The GitHub Personal Access Token you enter in the sync setup is stored in
`localStorage` in your browser only. It's never sent anywhere except
directly to `api.github.com`. Use a fine-grained token scoped to just the
repo you're syncing to.
