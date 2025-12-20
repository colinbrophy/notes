Core Capabilities of LLMs

A distilled model from discussion

Overview

Despite appearing to perform many tasks, LLMs exhibit only a small set of user-facing capabilities. Internally they perform conditional pattern completion, but from a practical perspective their behaviour can be reduced to three core abilities.

1. Deep Lookup

LLMs retrieve and recombine patterns from their training data in response to context.
This appears as:

Question answering

Explanations

Comparisons

Domain recall

Surfacing related concepts

Lookup is not factual certainty, but pattern-based retrieval influenced by prompt context.

2. Deep Translation

LLMs can re express information while keeping the underlying meaning or structure.
This includes:

Summaries

Rewrites

Style changes

Turning prose into code, tables or tests

Mapping concepts between domains

Normalising or reorganising messy information

Translation is where most productive uses lie (documentation cleanup, [[Anki]] card generation, knowledge distillation).

3. Pattern Recombination (Constrained Idea Generation)

LLMs generate plausible variations, alternatives and analogues based on known patterns.
Useful for:

Brainstorming

Producing design alternatives

Exploring edge cases

Creating analogies

Filling conceptual gaps

This is not creativity in the human sense and requires human judgement to evaluate.

What LLMs Cannot Reliably Do

These fall outside the three capabilities:

Grounded or causal reasoning

Maintaining invariants over long tasks

Detecting when they are wrong

Self correction without feedback

Handling complex, evolving goals

Long horizon architectural or modelling work

Summary

All reliable LLM behaviours can be framed as a mix of:

Lookup

Translation

Recombination

Everything else is an emergent impression. Understanding these limits clarifies where LLMs genuinely help and where human reasoning is required.