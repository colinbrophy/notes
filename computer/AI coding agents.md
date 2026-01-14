#draft #ai-written

## Overview

AI coding agents (e.g. [[Claude Code]], [[Codex]]) can be effective on
non-trivial codebases, but they fail in predictable ways:

- Plans bloat and drift
- Work gets skipped or half-done
- “Progress tracking” moves out-of-band into piles of docs
- You end up reconciling reports with reality instead of verifying code

This note captures the heuristics. For the practical loop, see
[[AI coding agent workflow]].

## Dijkstra lens (EWD 667)

[[Dijkstra - On the foolishness of natural language programming (EWD 667)]] frames the core failure mode:

- A wider interface doesn’t remove work; it adds coordination/translation work.
- Formal systems reject nonsense early; natural language lets nonsense hide.

Why this matters for agents:

- “Good prompts become code” is you narrowing the interface to regain precision.
- The machine burden shows up to you as latency (serial intent reconstruction).
- Use vagueness only while decisions are reversible (e.g. prototypes); avoid it where invariants must hold (e.g. security).

### Counterpoint: why vagueness can win

- Humans often have an evaluator before a spec (“I’ll know it when I see it”); natural language expresses partial constraints while keeping degrees of freedom open.
- This is powerful when decisions are reversible and evaluation is cheap (preview/tests/benchmarks); it’s basically search via candidates.
- It becomes dangerous when invariants must hold (security/concurrency/money): you need formal filters (types/tests/specs/threat model) to reject nonsense early.

See also: [[Tacit knowledge]].

## Taste, care, and stakes

- “Taste” is mostly **negative knowledge**: knowing what not to build, from past costs.
- Agents optimise for plausible completion, not restraint or long‑horizon coherence.
- Care comes from social + temporal stakes (maintenance pain, reputation, future readers); agents have none.
- RL / preference tuning shapes short‑horizon approval but does not create ownership.
- Taste evals are comparative and noisy; pairwise choices help but Goodhart quickly.
- Practical response: tighter constraints, cheap verification, and smaller horizons.

## When to use an agent (3-question rule)

Use an agent only if all are true:

- **“Done” is checkable up front** (tests/commands/examples).
- **First draft can be wrong** (discard is acceptable).
- **Mostly execution, not design** (plumbing/boilerplate/refactors/tests/doc→code).

If any is false: it’s a latency tax to avoid thinking.

## Parallelism (hiding latency)

- Parallelise **uncertainty** (spikes/competing designs), not shared-state execution.
- Cap at **1–2 agent worktrees**.
- Don’t steer mid-flight; review at the end.

Practical workflow: [[AI coding agent workflow]].

See also: [[Evergreen skills for AI-assisted coding]].
