# Dynamic Learning in AI vs Biology

## Context / Problem Statement
Modern AI systems (including LLMs) learn largely offline and are poor at dynamic, continual, online learning. Biological brains update continuously without catastrophic failure. The question is why this works biologically, why it is hard to replicate in AI, and whether current architectures are near a solution or facing a brick wall.

---

## Key Insights / Conclusions

### 1. Symbolic vs Neural AI
- Symbolic AI excelled at exact, formal, non-human tasks (logic, planning, optimisation).
- Neural systems excel at perception, learning, and approximation.
- Both are genuine AI; symbolic AI failed as a *theory of mind*, not as a technology.
- LLMs inherit neural weaknesses: poor guarantees, weak exact reasoning, unreliable constraints.

### 2. Smoothness Tradeoff
- Smooth, differentiable representations enable learning.
- The same smoothness undermines reliability, sharp boundaries, and guarantees.
- This is a structural tradeoff, not an implementation bug.

### 3. Why Dynamic Learning Is Hard in AI
- Online updates destabilise global models.
- Catastrophic forgetting and drift are hard to prevent.
- Safety, reproducibility, and control requirements rule out free self-modification.
- No existing architecture cleanly supports continual learning at scale.

### 4. Why Biology Can Update Dynamically
Biological learning works because it is:
- **Gated**: plasticity is conditional and rare
- **Local**: updates occur at individual synapses
- **Bounded**: changes are small and reversible
- **Compartmentalised**: fast memory vs slow memory systems
- **Redundant**: population coding absorbs error
- **Homeostatic**: automatic stabilisation counters drift
- **Embodied**: the environment provides constant corrective feedback

Stability is prioritised over optimality.

### 5. Role of Evolution
- Evolution tunes inductive biases, architectures, and learning rules, not solutions.
- It acts as an outer-loop optimiser over millions of failures.
- It constrains learning so heavily that simple local rules suffice.
- This process is slow, wasteful, and incompatible with engineering constraints.

### 6. Current AI Lab Approaches
- Continual learning methods (limited success)
- External memory and tool use
- Modular and mixture-of-experts architectures
- Meta-learning and in-context adaptation
- Neuro-inspired plasticity (research-stage)
- Hybrid neural-symbolic systems (most practical)

None solve the general problem.

### 7. State of the Field
- No sense of a hard brick wall
- No expectation of a near-term breakthrough
- Progress is incremental and architectural, not scaling-based

---

## Open Questions / Uncertainties
- Can learning be safely separated across timescales in deployed systems?
- Can we engineer reliable homeostasis and plasticity gating?
- Is structural growth necessary for continual learning?
- Are symbolic components unavoidable for reliability?

---

## Next Actions / Follow-ups
- Track research in continual learning and modular architectures
- Examine hybrid systems in planning, verification, and tool use
- Clarify which applications truly require online learning
- Accept architectural pluralism rather than single-paradigm solutions

---
