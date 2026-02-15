# ChatGPT Export Viewer (Enhanced)

A single-file, local-first viewer for large ChatGPT `conversations.json` exports.

This project is designed for offline/private use in your browser, with fast filtering, model controls, tags/notes, and better export tools for real-world archive cleanup.

## What It Does

- Loads ChatGPT export JSON locally (`conversations.json` style).
- Browses and searches large conversation sets.
- Filters by model, tags, favorites, and date.
- Supports in-conversation search with hit navigation.
- Adds per-conversation tags + notes (persisted locally).
- Supports data backup/import for settings + metadata.
- Exports/copies/prints either visible-only or full conversation content.

## Quick Start

1. Download `chatgpt_export_viewer_conversations.html`.
2. Open it in a modern browser.
3. Click `load json` (or drag/drop your JSON file).
4. Browse/filter conversations from the left panel.

No build tools or server required.

## Main Features

### Conversation List (Left Panel)

- Search box supports:
  - Plain text
  - `m/<model>` quick search
  - `t/<tag>` quick search
- Sort dropdown (`updated/created`, ascending/descending).
- Favorites filter.
- Single-tag filter (`all tags`, specific tags, `none`).
- Clickable model chips and tag chips in each conversation row.
- Active conversation highlighting.
- Resizable left panel.

### Advanced Filters (Top "More" Panel)

- `whole word` search mode.
- `title` mode (search titles only).
- `raw tool text` toggle for searching tool/function payload text.
- Date search block:
  - Field: `updated` or `created`
  - `from` / `to` range
- Tag filters:
  - Multi-select tags
  - Modes: `any`, `all`, `only`
- Clear filters action.

### Tag Manager Panel

- Bulk operations on currently filtered conversations:
  - Add tag to filtered
  - Remove tag from filtered
- Advanced global tag maintenance:
  - Rename a tag everywhere
  - Merge one tag into another
  - Delete a tag everywhere
- Tag counts in manager dropdowns.

### Conversation View (Right Panel)

- Sticky in-conversation find bar:
  - Query input
  - Whole word toggle
  - Full conversation toggle
  - Prev/next hit navigation
  - Top/bottom scroll shortcuts
- Header with:
  - Title, dates, message/model stats, last model used
  - Models used
  - Conversation ID
  - Favorites toggle
  - Tag editor
  - Notes editor
- Per-message copy button.

### Hidden/Filtered Match Visibility

When full-conversation find is enabled, the viewer can show details for matches that are not currently visible in rendered message segments (for example tool payload content filtered from the main thread view).

### Export / Copy / Print Modes

Per conversation, choose:

- `visible only`: export/copy/print only currently visible message entries.
- `full convo`: export/copy/print full conversation (excluding empty system messages).

### Persistence and Backup

- `localStorage` saves UI state and metadata:
  - Filters
  - Model toggles
  - Favorites
  - Tags
  - Notes
  - Layout/UI states
- IndexedDB caches the last loaded JSON for auto-restore on reopen.
- Export/import settings metadata JSON (`export data` / `import data`).

## Keyboard Shortcuts

- `j` or `ArrowDown`: next conversation
- `k` or `ArrowUp`: previous conversation
- In convo find box: `Enter` next hit, `Shift+Enter` previous hit

## Notes

- This tool is local-first and intended for personal archives.
- Large exports can still be heavy depending on browser/device memory.
- Tool/function memory payloads in exports may be partial, verbose, or backend-dependent.

## File Layout

- `chatgpt_export_viewer_conversations.html` - app (single-file viewer)
- `conversations.json` - sample/export input file

## License

This project is licensed under the MIT License. See `LICENSE`.

## Privacy

- Runs locally in your browser.
- Does not require a backend/server.
- Reads only the JSON file you provide.
- Stores viewer state, tags, notes, and favorites in your browser (`localStorage`) and caches last JSON in IndexedDB for convenience.
- If you share screenshots or exported text, review/redact sensitive content first.
