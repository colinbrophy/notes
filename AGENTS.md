# Repository Guidelines

## Project Structure & Module Organization
- Plain Obsidian vault; everything is Markdown unless noted. Top-level notes live beside thematic folders.
- Key folders: `Diary/` (dated daily logs), `computer/` (technical how-tos), `languages/` (language study), `letby/` (case research), `maths/` (math essays), `.obsidian/` (editor config). Keep images/PDFs next to the referencing note.

## Build, Test, and Development Commands
- No build pipeline; work is text-first. Use `git status -sb` to see pending edits.
- Search quickly with `rg "search term"` from the vault root.
- Review changes with `git diff` before committing to catch formatting/link issues.

## Coding Style & Naming Conventions
- Use Markdown headings and hyphen bullets; prefer fenced code blocks with language hints for commands.
- File naming: `Diary/YYYY-MM-DD.md` for daily entries; topical notes use short, descriptive titles (spaces allowed). Avoid renaming existing files to preserve backlinks.
- Default to ASCII unless a note already uses specific symbols; avoid editing `.base` files unless you know their consumer.

## Testing Guidelines
- No automated tests. Manually check that headings are hierarchical, code blocks render, and media or internal links resolve.
- For sensitive topics, re-read for clarity, sourcing, and tone; avoid duplicating content across notes without cross-references.

## Commit & Pull Request Guidelines
- Recent history uses `vault backup: YYYY-MM-DD HH:MM:SS` for bulk syncs. For focused edits, prefer concise, imperative summaries (e.g., `update diary entry`, `add youtube cli cheatsheet`).
- Commit after reviewing `git status` and `git diff`; avoid bundling unrelated areas together.
- If opening a PR, include a brief summary, mention sensitive additions, and flag files likely to conflict (e.g., same-day diary entries).

## Security & Privacy
- Vault may contain personal information. Don’t add credentials, tokens, or private third-party data. Redact sensitive details before committing and avoid large binaries unless essential.
