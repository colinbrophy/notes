#draft #ai-written

Practical loop for [[AI coding agents]].

## Core idea: put unfinished work in the code

When you discover missing work, don’t write another plan document.
Insert explicit, local TODO stubs directly where the missing behaviour
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

## Gates (before merging)

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

## Failure modes / counterpoints

- TODOs get noisy if they’re vague or unowned
- “Code complete” claims can be false if TODOs remain (treat TODOs as open work)
- Some work is too large for one patch: split into narrower TODOs, but keep
  *implementation gaps* in-code

