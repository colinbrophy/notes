#draft #ai-written

## Overview

AI coding agents (e.g. [[Claude Code]], [[Codex]]) can be effective on
non-trivial codebases, but they fail in predictable ways:

- Plans bloat and drift
- Work gets skipped or half-done
- “Progress tracking” moves out-of-band into piles of docs
- You end up reconciling reports with reality instead of verifying code

This note captures a practical control loop: keep scope small, keep the
repo as the source of truth, and make “done” verifiable.

## Core insight: put unfinished work in the code

When you discover missing work, don’t write another plan document.
Insert explicit, local TODO stubs directly where the missing work
belongs.

Effects:

- The codebase becomes the source of truth (no document drift)
- Outstanding work is visible in context
- Completion is self-cleaning (remove the TODO when done)
- Agents operate on small, local tasks (their sweet spot)

## Workflow

### 1) Establish invariants

- One task = one PR (or one patchset)
- One TODO (or a tight cluster) per agent run
- Every change has a verification step (test, lint, runtime check, or a
  concrete observable behaviour change)
- If the agent is uncertain: add a narrower TODO, don’t invent a bigger
  plan

### 2) Task intake: write TODOs in place

When analysis finds gaps, write TODOs in the relevant file(s), close to
the missing behaviour. Avoid vague TODOs.

Include:

- What is missing, and why
- Acceptance criteria (observable outcomes)
- How to verify (tests/commands)
- Constraints/dependencies (if any)

### 3) Task selection

- Enumerate TODOs via a deterministic script (`rg`, CI, static analysis)
- Pick the smallest valuable TODO first
- Keep patches serialisable (easy to review, easy to revert)

### 4) Implement + verify + remove TODO

- Provide the agent only the files needed for that TODO
- Require: implementation + verification + running the checks
- Close the loop by deleting the TODO when it’s done

### Gates (before merging)

- Format
- Lint / static analysis
- Unit tests
- Integration / end-to-end tests (if relevant)
- Minimal review checklist (correctness, edge cases, security, rollback)

## TODO template

Use something like:

- `TODO(<tag>): <action> because <reason>`
- `Acceptance: <specific outcomes>`
- `Verify: <tests/commands>`
- Optional: `Deps: <files/components>`

If you later need a taxonomy, decide it explicitly (don’t let it emerge
accidentally).

## Minimal commands

Enumerate TODOs:

```bash
rg -n "\\bTODO\\b" .
rg -n "TODO\\(" .   # if you standardise TODO(TAG):
```

Verification examples (project-specific):

```bash
go test ./...
golangci-lint run
```

## Failure modes / counterpoints

- TODOs can get noisy if they are vague or unowned
- “Code complete” claims can be false if TODOs remain (treat TODOs as
  open work)
- Some work is too large for one patch: split into narrower TODOs or
  track as an external “epic” (but keep *implementation gaps* in-code)

## Variants seen in the wild

- “List TODOs” as a slash command (but keep the underlying mechanism
  deterministic)
- Design by Contract: contracts as “executable TODOs” (fail loudly when
  a spec isn’t met)
- Heavier process frameworks (BMAD/SDD/GSD): potentially useful, but easy
  to overdo and reintroduce plan bloat

## Open questions

- Do I want a TODO taxonomy (feature/bug/perf/security/refactor), or keep
  it flat?
- Where should “bigger than one PR” work live (issue tracker, epic note,
  ADR)?
- What hard limits should be set for agent runs (time, file count, diff
  size)?
