# Repository Guidelines

## Project Structure & Module Organization
- Plain [[Obsidian]] vault; everything is Markdown unless noted. Top-level notes live beside thematic folders.
- Key folders: `diary/` (dated daily logs), `computer/` (technical how-tos), `languages/` (language study), `letby/` (case research), `maths/` (math essays), `productivity/` (process notes), `external_dumps/` (imports/inbox), `rough_notes/` (scratchpad), `.obsidian/` (editor config). Keep images/PDFs next to the referencing note.

## Build, Test, and Development Commands
- No build pipeline; work is text-first. Use `git status -sb` to see pending edits.
- Search quickly with `rg "search term"` from the vault root.
- Review changes with `git diff` before committing to catch formatting/link issues.

## Coding Style & Naming Conventions
- Use Markdown headings and hyphen bullets; prefer fenced code blocks with language hints for commands.
- File naming: `diary/YYYY-MM-DD.md` for daily entries; topical notes use short, descriptive titles (spaces allowed). Avoid renaming existing files to preserve backlinks.
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

## Skills
These skills are discovered at startup from multiple local sources. Each entry includes a name, description, and file path so you can open the source for full instructions.
- skill-creator: Guide for creating effective skills. This skill should be used when users want to create a new skill (or update an existing skill) that extends Codex's capabilities with specialized knowledge, workflows, or tool integrations. (file: /home/colinbrophy/.codex/skills/.system/skill-creator/SKILL.md)
- skill-installer: Install Codex skills into $CODEX_HOME/skills from a curated list or a GitHub repo path. Use when a user asks to list installable skills, install a curated skill, or install a skill from another repo (including private repos). (file: /home/colinbrophy/.codex/skills/.system/skill-installer/SKILL.md)
- Discovery: Available skills are listed in project docs and may also appear in a runtime "## Skills" section (name + description + file path). These are the sources of truth; skill bodies live on disk at the listed paths.
- Trigger rules: If the user names a skill (with `$SkillName` or plain text) OR the task clearly matches a skill's description, you must use that skill for that turn. Multiple mentions mean use them all. Do not carry skills across turns unless re-mentioned.
- Missing/blocked: If a named skill isn't in the list or the path can't be read, say so briefly and continue with the best fallback.
- How to use a skill (progressive disclosure):
  1) After deciding to use a skill, open its `SKILL.md`. Read only enough to follow the workflow.
  2) If `SKILL.md` points to extra folders such as `references/`, load only the specific files needed for the request; don't bulk-load everything.
  3) If `scripts/` exist, prefer running or patching them instead of retyping large code blocks.
  4) If `assets/` or templates exist, reuse them instead of recreating from scratch.
- Description as trigger: The YAML `description` in `SKILL.md` is the primary trigger signal; rely on it to decide applicability. If unsure, ask a brief clarification before proceeding.
- Coordination and sequencing:
  - If multiple skills apply, choose the minimal set that covers the request and state the order you'll use them.
  - Announce which skill(s) you're using and why (one short line). If you skip an obvious skill, say why.
- Context hygiene:
  - Keep context small: summarize long sections instead of pasting them; only load extra files when needed.
  - Avoid deeply nested references; prefer one-hop files explicitly linked from `SKILL.md`.
  - When variants exist (frameworks, providers, domains), pick only the relevant reference file(s) and note that choice.
- Safety and fallback: If a skill can't be applied cleanly (missing files, unclear instructions), state the issue, pick the next-best approach, and continue.
