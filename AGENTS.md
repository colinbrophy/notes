# Repository Guidelines

## Project Structure & Module Organization
- This repo is a plain **Obsidian vault**: Markdown notes plus a few local attachments (PDF/PNG/DOCX).
- Thematic folders: `computer/`, `maths/`, `letby/`, `languages/`, `productivity/`, `external_dumps/`, `diary/`.
- Scratch work lives in `rough_notes/` (don’t treat as curated unless explicitly asked).
- Keep attachments next to the note that references them (e.g., `letby/Baby C floor.png` linked via `![[Baby C floor.png]]`).
- `.obsidian/` is editor config; avoid committing machine-specific state unless intentional.

## Build, Test, and Development Commands
- No build/test pipeline (text-first repo).
- Useful commands from the vault root:
  - `git status -sb` — see pending edits.
  - `git diff` — review changes before committing.
  - `rg "search term"` — fast full-text search.

## Coding Style & Naming Conventions
- Markdown: hierarchical headings, hyphen bullets, and fenced code blocks with language hints (e.g., ```bash).
- Directories: lowercase with underscores (already normalized).
- Files:
  - Daily notes: `diary/YYYY-MM-DD.md`
  - Everything else: short, descriptive titles (spaces allowed). Avoid renaming files to preserve backlinks.
- Notes: prefer **atomic concept notes** (one main idea per note). Avoid creating mixed-topic notes (e.g., “LLM (shell pipes)”)—instead add a section to an existing concept note and link out to other concepts.
- Linking philosophy:
  - **Concepts** → empty notes as stable anchors (e.g., `Go (programming language).md`).
  - When a new concept is mentioned, create a corresponding (even empty) note and reference it with Obsidian `[[wikilinks]]` so it has backlinks and doesn’t become “floating text”.
  - **Properties/states** → tags (e.g., `#todo`, `#draft`, `#question`, `#low-confidence`).

## Testing Guidelines
- Manual checks only: open the note(s) in Obsidian and confirm headings render, code blocks format, and links/embeds resolve.

## Commit & Pull Request Guidelines
- Commit messages:
  - Bulk sync: `vault backup: YYYY-MM-DD HH:MM:SS`
  - Focused edits: short, imperative (e.g., `add tag system`, `fix broken links`)
- Keep commits scoped; avoid mixing unrelated areas (especially `diary/` with refactors).

## Security & Privacy
- Don’t commit credentials or private third‑party data. Redact sensitive details. Avoid large binaries unless necessary.
