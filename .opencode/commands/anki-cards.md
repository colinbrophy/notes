---
description: Create dated atomic Anki cards from notes
---

Follow @AGENTS.md.

Create Anki cards using this workflow:

Current git status:
!`git status --short`

Today's date:
!`date +%F`

Inputs:
- Command arguments: `$ARGUMENTS`

Steps:
1. Choose source files:
   - If `$ARGUMENTS` is non-empty, use those file paths as sources.
   - Otherwise, use modified/untracked Markdown files from git status.
2. Read the source files and extract card-worthy facts.
3. Cards must be atomic: exactly one fact/command/concept per card.
4. Avoid duplicates by checking existing `anki/**/*.txt` cards.
5. Create one new output file under `anki/YYYY-MM-DD/` (today's date), creating the date folder if needed.
   - Use tab-separated format: `Front<TAB>Back`.
   - Use a descriptive filename such as `newanki-<topic>.txt`.
6. Do not modify existing Anki files unless explicitly asked.
7. Return a short report with:
   - Source files used
   - Output file path
   - Number of cards created
   - Any files skipped (empty/no card-worthy content)
