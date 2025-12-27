# Repository Guidelines

## Project Structure & Module Organization
- This repo is a plain **Obsidian vault**: Markdown notes plus a few local attachments (PDF/PNG/DOCX).
- Thematic folders: `computer/`, `maths/`, `letby/`, `languages/`, `productivity/`, `external_dumps/`, `diary/`.
- Scratch work lives in `rough_notes/` (don’t treat as curated unless explicitly asked).
- Keep attachments next to the note that references them (e.g., `letby/Baby C floor.png` linked via `![[Baby C floor.png]]`).
- `.obsidian/` is editor config; avoid committing machine-specific state unless intentional.

## Coding Style & Naming Conventions
- Markdown: hierarchical headings, hyphen bullets, and fenced code blocks with language hints (e.g., ```bash).
- Directories: lowercase with underscores (already normalized).
- Files:
  - Daily notes: `diary/YYYY-MM-DD.md`
  - Everything else: short, descriptive titles (spaces allowed). Avoid renaming files to preserve backlinks.
- Notes: prefer **atomic concept notes** (one main idea per note). Avoid creating mixed-topic notes (e.g., “LLM (shell pipes)”)—instead add a section to an existing concept note and link out to other concepts.
- Linking philosophy:
  - **Concepts** → empty notes as stable anchors (e.g., `Go (programming language).md`).
  - Prefer Obsidian `[[wikilinks]]` for concepts so ideas stay linkable and discoverable.
  - Do **not** automatically create placeholder/stub notes for every linked concept; only create new concept notes when explicitly asked or when the concept is central to the current work.
  - **Properties/states** → tags (e.g., `#todo`, `#draft`, `#question`, `#low-confidence`).
  - Tags: check `Tags.md` before inventing new tags; if a new tag is needed, document it there.
  - AI-assisted writing: tag notes written primarily by an AI assistant with `#ai-written` (and treat as rough until verified/edited).
  - Division of labour: you decide what matters (selection); the assistant focuses on translation (remove fluff, restructure, rephrase) rather than inventing importance hierarchies.
  - What to capture: prefer notes that encode your own heuristics/stances and information that is hard to look up again; avoid Wikipedia-style neutral facts that are easy to re-find.
  - Respect intentional edits: if you delete or change something on purpose, don’t “fix” it by reintroducing the old content; ignore unrelated changes unless explicitly asked.

## Testing Guidelines
- Manual checks only: open the note(s) in Obsidian and confirm headings render, code blocks format, and links/embeds resolve.

## Commit & Pull Request Guidelines
- Commit messages:
  - Bulk sync: `vault backup: YYYY-MM-DD HH:MM:SS`
  - Focused edits: short, imperative (e.g., `add tag system`, `fix broken links`)
- Keep commits scoped; avoid mixing unrelated areas (especially `diary/` with refactors).
- **Never discard changes without asking**: do not run `git restore`, `git checkout -- <file>`, `git reset`, or similar on files the user didn’t explicitly ask you to revert. If unrelated edits are present, ask whether to keep them, split them into a separate commit, or discard them.

## Security & Privacy
- Don’t commit credentials or private third‑party data. Redact sensitive details. Avoid large binaries unless necessary.
