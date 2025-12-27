---
tags: [draft, ai-written]
---

## Context / goal

Rough capture of a thread about:

- why NVIDIA invests directly into AI companies
- whether the “circularity” is fragile / ponzi-like
- what the actual business synergy is
- uncertainty about AI futures (winter vs “AGI-ish”)
- why current systems “lose the plot” over long horizons (and why scaffolding may not scale)

Cleanup later into atomic notes if it’s worth it.

## NVIDIA investing in AI companies: why

Claim: NVIDIA invests directly to strengthen the ecosystem that drives demand for its core (GPUs + software stack).

Reasons discussed:

- creates more workloads that consume NVIDIA compute
- reduces platform execution risk (keep CUDA/tooling central)
- gets early visibility into emerging workloads (inform roadmap)
- strengthens path dependence / lock-in (startups grow inside the stack)
- optional equity upside is secondary to utilisation

## “It’s circular” → yes, deliberately

The “circle” described:

1. NVIDIA funds AI companies.
2. They build products that require compute.
3. The easiest compute is NVIDIA’s stack.
4. Demand for NVIDIA hardware increases.
5. NVIDIA gets cash/influence and repeats.

Framed as a positive feedback loop, not a flaw, provided the base assumptions hold:

- compute demand is real and growing
- switching costs are high once committed to CUDA/tooling
- substitutes are not at parity

## Not a Ponzi (but asymmetry is real)

Why “Ponzi” doesn’t fit:

- NVIDIA revenue comes from selling hardware/software to do real work, not paying earlier investors with later investors’ money
- productive activity exists underneath (training/inference is real even if valuations are frothy)
- no promised/guaranteed returns; normal market risk applies

But the structural asymmetry is real:

- upstream infrastructure providers can capture rents
- downstream app startups (and their investors) face brutal competition and may lose even if “AI wins”

So the correct critique is more like:

- ecosystem capture / market power entrenchment / vertical coordination pressure
- antitrust / industrial policy questions

## “Why can startups raise only via NVIDIA?”

Answer: they can’t *only*, but NVIDIA’s capital is uniquely valuable because it bundles things VCs can’t provide:

- preferential access to scarce compute (capacity)
- engineering optimisation support
- signalling (“certification”) to customers and other investors
- path dependence (if you commit early, switching is costly)

Key asymmetry: VCs need exits; NVIDIA mostly needs utilisation.

## What is the mutually beneficial deal?

Startup gets:

- compute certainty (scarcity insurance)
- time-to-train / iteration speed (time is existential)
- credibility + survival odds

NVIDIA gets:

- committed demand (training + inference load)
- stack standardisation via path dependence
- early visibility into which workloads matter
- equity upside is secondary

One-liner: NVIDIA trades compute certainty for ecosystem capture; startups trade independence for survival.

## Where is the “business synergy”?

Framing: capacity insurance → demand certainty.

- NVIDIA is capital-intensive with long lead times; demand uncertainty is catastrophic.
- Startups are compute-constrained; cash alone doesn’t unblock timelines.

So the “investment” functions like a coordination/offtake mechanism:

- NVIDIA effectively pre-sells future output by anchoring downstream users.
- Startups pull compute forward in time to avoid missing market windows.

## “Diversification / insurance” angle

Reframe: NVIDIA is not diversifying across exits; it is diversifying across **outcomes that all burn compute**.

- NVIDIA is upstream of many downstream failure modes.
- GPU consumption happens early (before “success” is known).
- Even failed startups can be “wins” in utilisation terms.

The undiversifiable risk: the entire class of AI workloads fails to justify its compute intensity (demand shock).

## Coordination failure (the deadlock)

Deadlock:

- NVIDIA doesn’t want to fully commit to supply without demand certainty.
- AI labs/startups don’t want to commit capital/plans without supply certainty.

NVIDIA acts as coordinator by investing to synchronise both sides:

- signals credible future demand to itself/supply chain
- signals credible future supply to startups/investors

## Big picture uncertainty: winter vs discontinuity

Two coherent futures outlined:

- scaling stalls → AI normalises as tools/infrastructure; capital retreats (“winter” but with residue)
- scaling holds → capabilities compound; integration (memory/tools/planning) accelerates disruption

Also plausible: winter first, later resurgence if a new idea/architecture unlocks a new regime.

Key point: irreducible regime uncertainty; there is no cheap experiment and no decisive sign yet.

## “Missing ingredient”: dynamic social learning / intent grounding

Hypothesis: current systems learn offline and lack open-ended social grounding:

- norms / roles / reputation / obligations
- long-horizon identity/commitment mechanisms

This might be orthogonal to scaling (may need architectural machinery, not just bigger models).

## Can RL-on-LLMs solve it?

Claim: RL layers can improve *behavioural adaptation* (task-following, tool use, preference fitting) but don’t obviously create:

- intent grounding (human intent isn’t a stable scalar reward)
- norm internalisation (constraint without monitoring)
- identity-level persistence

Also: reward hacking / proxy optimisation (“Goodharting”) tends to scale with capability.

## “Losing the plot” over long horizons

Observed failure mode:

- drift in goals/framing
- forget why earlier steps were taken
- local optimisation breaks the global plan
- inconsistencies accumulate until coherence collapses

Hypothesis: this is structural:

- no persistent internal goals/commitments (only prompts + context + token policy)
- training signals are short-horizon/episodic even when tasks are long
- memory stores facts, not “what is binding”
- no internal dissonance / norm pressure / reputational cost to trigger repair

Humans don’t have a clean utility function, but do have persistence mechanisms:

- identity-based continuity
- commitments (promises/contracts/moral obligations)
- narrative memory (meaning-preserving)
- norm internalisation and social accountability

## Why scaffolding may not scale

Claim: scaffolding works by repeatedly re-injecting intent (plans, summaries, constraints), but:

- each re-representation compresses/reinterprets meaning
- drift accumulates with horizon (more turns → more summarisation → more semantic error)
- tokens describe goals; commitments constrain behaviour
- self-critique uses the same policy and drifts too unless anchored by an external standard
- more memory increases inconsistency surface area without a hierarchy of binding constraints

Conclusion from the thread: companies can mitigate drift with engineering (planning loops, memory, verifiers), but the identity/commitment/social-grounding mechanism is still an open frontier.

## Pointers for vault integration later

Potential splits if this becomes useful:

- NVIDIA as coordinator / demand-insurance loop (infrastructure economics)
- “reasoning vs social grounding” as the missing ingredient
- long-horizon coherence: commitments vs tokens; why scaffolding drifts

Existing notes that might be adjacent:

- [[Capitalism]]
- [[Emergence]]
- [[LLMs]]
