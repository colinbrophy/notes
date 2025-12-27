---
tags: [draft]
---

## Context / goal

There’s an “insight cluster” here about why local LLMs can *feel* better for daily dev work than cloud tools, even when cloud has better overall capability.

This is a rough capture; split into atomic notes later.

## Key distinction: throughput vs felt speed

- **Tokens/sec (TPS)** is steady-state generation rate once output is streaming.
- **Time to first token (TTFT)** dominates whether something feels “instant”.

Rule-of-thumb “instant” cliff (human factors):

- < 100 ms: instantaneous
- 100–250 ms: still “instant”
- 250–500 ms: noticeable but usable
- 500–800 ms: flow degradation begins
- > 1 s: feels remote; flow breaks

After TTFT is good, TPS matters, but can’t compensate for slow TTFT in flow workflows.

## Local vs cloud (how to think about it)

- Local can be very fast on TPS for small/mid models if weights fit comfortably in VRAM and you use good runtimes/quantisation.
- Cloud often wins at “reasoning per second” and “reliability per request” because it’s not just a model: it’s orchestration + retries + verifiers + caching + infra tricks.

So:

- Cloud tends to win at “deep solve this ambiguous thing”.
- Local tends to win at “rapid iteration / lookup / keep flow”.

## Model size for “vibe coding”

Heuristic tiers (not gospel):

- Basic vibe coding (snippets/boilerplate/refactors): 7B–13B can be enough.
- “Build me an app” vibe coding (multi-file coherence): 13B feels like a threshold; 20B–34B is comfy; 70B+ often harms flow via latency.

Context window often matters more than params for dev workflows (being able to paste a whole doc or file and ask a bounded question).

## Why Codex / Claude Code feel “better than raw local models”

The experience is mostly architecture, not raw parameter count:

- planner/executor separation (think rarely, type fast)
- cached decisions/constraints instead of replaying chat history
- diff/patch edits instead of “rewrite entire file”
- verification and retry loops (you only see the filtered output)
- context selection: relevant slices, not “everything so far”

The “big beast” model (if present) is used off the critical path for planning/arbitration; most visible output comes from a faster executor.

## The killer workflow: use LLMs as readers, not oracles

Hallucination risk spikes when you ask the model to answer from internal knowledge for precise technical detail (flags, options, exact behaviour).

The safer pattern:

- choose the authoritative text yourself (man page, `--help`, official docs, source)
- feed it in full
- ask a narrow question
- allow “not found” as a valid answer

This is “retrieval” (reading provided text), not “recall” (guessing).

## Shell pipes are the right abstraction

Desired UX:

- stdin is the context (document)
- stdout is the answer
- low TTFT
- stateless unless explicitly asked

Example shape (tool placeholder: charmbracelet/mods):

```bash
man foo | mods "Using only the text above: how do I do X? If not present say 'not found'."
```

This aligns with [[UNIX]]: composability, bounded context, inspectable text streams.

## Why search is now painful for this

- SEO sludge / paraphrased docs / “summaries of summaries”
- canonical docs are harder to reach
- LLM+search often reintroduces missing evidence → model guesses → hallucination

Better loop for technical work:

- go directly to canonical docs/source/man pages
- pipe the text to an LLM for extraction/explanation

## Next cleanup directions

- Add a “LLM as UNIX filter” section into [[LLMs]] (and link back from [[UNIX]]).
- Capture TTFT/TPS as distinct concepts (and keep them separate from model-size talk).
- Capture “planner/executor split” as a system pattern (separate from “big model” discourse).

