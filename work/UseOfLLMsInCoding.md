## The golden rule:

#### Use agents only when they shorten time‑to‑feedback, not when they “write more code”.

**The friction reality:**
- GUI friction is invisible but compounds
- LLM friction is worse: hallucination, lost context, verification tax, re-prompting
- Natural language is harder to learn than CLI by orders of magnitude—unbounded, no spec, shifts underneath you. CLI is finite and knowable.

**Where LLMs are genuinely faster (even for the CLI/neovim wizard):**
- Idea exploration
- Translation (where no deterministic transpiler exists; includes docs)
- Semantic transforms beyond regex/LSP
- Spot explanations in unfamiliar code
- Deep lookup (well-documented tools, poorly indexed by intent—the ffmpeg problem)

**The discipline:**
- Don't use LLMs for what your tools can do
- Slop trap: LLMs reduce the cost of producing “app-shaped” artifacts (e.g. yet another TODO app)
- Counter: learn narrow primitives (editor + CLI) so you can solve many “little apps” as compositions (pipes + text + exit codes), not projects
- Skill atrophy is worse here than with autocomplete—you lose the skill AND the replacement is unreliable
- METR study: devs were 19% slower on familiar codebases with AI, while believing they were faster

**Iteration (time-to-signal):**
- Don't generate many candidates unless evaluation is cheap (preview/tests/benchmarks/canaries)
- Agents should shorten time-to-signal (repros, instrumentation, concrete checks), not just generate code
- LLM-written tests are noise unless anchored (regression, golden example, explicit invariant)
- Semantic search is a latency trade: use it when you don't know the words; keep lexical search as default

**The pattern:**
The LLM is a narrow tool for specific gaps where verification is cheap. For everything else, the CLI/neovim user is faster and more reliable. The people who think LLMs remove the need to learn tools have it exactly backwards—the LLM is a lookup accelerator for people who already know what good looks like.

---

## AI coding agent workflow

Practical loop for [[AI coding agents]].

### Core idea: put unfinished work in the code

When you discover missing work, don’t write another plan document.
Insert explicit, local TODO stubs directly where the missing behaviour
belongs.

Effects:

- The codebase becomes the source of truth (no document drift)
- Outstanding work is visible in context
- Completion is self-cleaning (remove the TODO when done)
- Agents operate on small, local tasks (their sweet spot)

### Workflow

#### 1) Establish invariants

- One task = one PR (or one patchset)
- One TODO (or a tight cluster) per agent run
- Every change has a verification step (test, lint, runtime check, or a
  concrete observable behaviour change)
- If the agent is uncertain: add a narrower TODO, don’t invent a bigger
  plan

#### 2) Task intake: write TODOs in place

When analysis finds gaps, write TODOs in the relevant file(s), close to
the missing behaviour. Avoid vague TODOs.

Include:

- What is missing, and why
- Acceptance criteria (observable outcomes)
- How to verify (tests/commands)
- Constraints/dependencies (if any)

#### 3) Task selection

- Enumerate TODOs via a deterministic script (`rg`, CI, static analysis)
- Pick the smallest valuable TODO first
- Keep patches serialisable (easy to review, easy to revert)

#### 4) Implement + verify + remove TODO

- Provide the agent only the files needed for that TODO
- Require: implementation + verification + running the checks
- Close the loop by deleting the TODO when it’s done

### Gates (before merging)

- Format
- Lint / static analysis
- Unit tests
- Integration / end-to-end tests (if relevant)
- Minimal review checklist (correctness, edge cases, security, rollback)

### TODO template

Use something like:

- `TODO(<tag>): <action> because <reason>`
- `Acceptance: <specific outcomes>`
- `Verify: <tests/commands>`
- Optional: `Deps: <files/components>`

### Failure modes / counterpoints

- TODOs get noisy if they’re vague or unowned
- “Code complete” claims can be false if TODOs remain (treat TODOs as open work)
- Some work is too large for one patch: split into narrower TODOs, but keep
  *implementation gaps* in-code

Related: [[Tacit knowledge]], [[Evergreen skills for AI-assisted coding]].
