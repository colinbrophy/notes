
Only really useful for:
## 1. Deep Lookup

LLMs retrieve and recombine patterns from their training data in
response to context. This appears as: - Question answering -
Explanations - Comparisons - Domain recall - Surfacing related concepts

Lookup is not factual certainty, but pattern-based retrieval influenced
by prompt context.

This is essentaily the role of good
## 2. Deep Translation

LLMs can re-express information while keeping the underlying meaning or
structure. This includes: - Summaries - Rewrites - Style changes -
Turning prose into code, tables or tests - Mapping concepts between
domains - Normalising or reorganising messy information

Translation is where most productive uses lie (documentation cleanup,
[[Anki]] card generation, knowledge distillation).

## 3. Pattern Recombination (Constrained Idea Generation)

LLMs generate plausible variations, alternatives and analogues based on
known patterns. 

**THIS IS THE MOST DANGEROUS USE OF AI, IDEA GENERATION IS CHEAP, TESTING IF THEY WORK IS HARD**

Only use this sparingly.

A good example of this is with note taking itself.


## Practical Use (Where They Shine)

### LLMs as readers (retrieval > recall)

For technical work, LLMs are most reliable as fast readers of
authoritative text you provide (man pages, `--help`, official docs,
source), not as oracles answering from internal knowledge.

This reduces hallucination because it turns the task into: “given this
text, answer this question”.

Default contract for precision:

- Use only the provided text
- If the answer is not present: say `not found`

This aligns naturally with [[UNIX]] pipes:

```bash
man foo | mods "Using only the text above: how do I do X? If not present say 'not found'."
```

Related concepts (not separate notes unless needed): tokens/sec (TPS), time to first token (TTFT)

### Felt speed: TTFT beats TPS

For interactive workflows, time to first token dominates “instant”
feeling more than raw throughput.

Rule-of-thumb cliff:

- < 100 ms: instantaneous
- 100–250 ms: still “instant”
- 250–500 ms: noticeable but usable
- 500–800 ms: flow degradation begins
- > 1 s: feels remote

### Local vs cloud (what “wins” depends on the metric)

- Cloud often wins at “reasoning per second” and “reliability per request” (orchestration, retries/verifiers, caching, batching/infra tricks).
- Local often wins at “flow” (low/consistent TTFT, no queueing/rate limits, fast iteration on your machine).

### Coding assistants are systems, not just models

Codex/Claude-code-style tools can feel better than “raw chat with a local model” mostly because of system design:

- planner/executor separation (think rarely, type fast)
- cached decisions/constraints (not replaying long chat history)
- diffs/patch edits rather than full-file rewrites
- verification + retries (you see the filtered output)
- selective context injection (relevant slices, not “everything so far”)

### Model size heuristics (for coding)

Heuristic tiers (not gospel):

- Basic [[Vibe coding]] (snippets/boilerplate/refactors): 7B–13B is often enough.
- “Build me an app” [[Vibe coding]] (multi-file coherence): ~13B feels like a threshold; 20B–34B is comfortable; 70B+ often harms flow via latency.

Context window often matters more than parameter count for “read this doc/file and answer this question”.

### Search vs canonical docs

For technical detail, search results increasingly contain SEO sludge and paraphrases of paraphrases.

Better loop:

- go straight to canonical docs/source/man pages
- pipe the text to an LLM for extraction/explanation

See also: [[Evergreen skills for AI-assisted coding]]. [[ChatGPT and Other chatbots]]
