---
tags: [draft, ai-written]
---

## Context / goal

Capture a long chat about RL scaling, information efficiency, reliability limits, and economic usefulness of agentic AI.

## Summary

### Core claims
- The shift from large-scale pretraining to RL-based post-training is a new scaling regime that is far less information-efficient.
- RL improves depth on narrow tasks but sacrifices generality; pretraining drove broad, unexpected capabilities.

### Pretraining vs RL (information efficiency)
- Pretraining: dense token-level signal (roughly a few to ~16 bits per token early; ~3 bits later), enabling rapid general gains.
- RL on long-horizon tasks: sparse rewards (often <1 bit per 10k–1M tokens), yielding ~1,000×–1,000,000× less learnable info per compute.
- Result: RL scales performance on specific tasks but does not reliably transfer across domains.

### Reliability math & horizon effects
- Long-horizon success scales as p^n (p = per-step correctness); small p increases can explode apparent horizon.
- 50% success sits on the steepest part of the curve and overstates robustness; tail failures remain dominant.
- Achieving 99% task success for 100-step tasks implies ~99.99% per-step correctness, a qualitatively harder regime.

### Why RL/synthetic data help but don’t “reset” scaling
- RL can shape behavior and recovery but cannot eliminate tail errors due to sparse signal and proxy rewards.
- Synthetic data is closer to pretraining (dense signal) and can distill latent reasoning, but risks self-referential closure.
- Expert-curated synthetic data can push p higher on a fixed distribution but faces steep marginal costs and coverage limits.

### Economics & practical usefulness
- 50% reliable long-horizon agents are rarely economical; verification costs dominate.
- Useful systems likely emphasize short, reliable segments with checkpoints and human oversight.
- Agents running for hours are less valuable than fast, interruptible tools for most programming work.

### Outlook
- Expect deceleration rather than a classic AI winter: fewer surprise capabilities, more reliability engineering.
- Benchmarks may reframe progress (new metrics, higher inference budgets), while economic constraints remain the anchor.

## Cleanup targets
- [[Reinforcement learning]]
- [[Pretraining]]
- [[Chain-of-thought]]
- [[Synthetic data]]
- [[Reliability (AI systems)]]
- [[Agentic AI]]
- [[Economic impact of AI]]
- [[AI winter]]

## Chat (verbatim)

Please summarise the selection using precise and concise language. Use headers and bullet-pointed lists in the summary, to make it scannable. Maintain the meaning and factual accuracy.



Below is a precise, scannable summary that preserves the meaning and factual accuracy of the original selection. 

pasted

Core Claim

The shift from large-scale pre-training to reinforcement learning represents a new scaling paradigm in AI.

This paradigm is dramatically less information-efficient, by roughly three to six orders of magnitude.

The change has major implications for future progress, especially for model generality.

Pre-training Era (2018–2023)

Dominated by next-token prediction on vast text corpora.

Scaling came primarily from increasing data and compute by up to one million times.

Each generated token provides several bits of learning signal.

High information efficiency enabled rapid gains in breadth and general capabilities.

Produced many unexpected, emergent abilities across diverse domains.

RL Scaling Era (2024–)

Focuses on post-training with reinforcement learning on reasoning and agentic tasks.

Uses long reasoning chains with sparse rewards.

Each training episode may involve thousands to millions of tokens before yielding a single bit of feedback.

Information gained per token is orders of magnitude lower than in pre-training.

Information Efficiency Comparison

Pre-training:

Early training: up to ~16 bits per token.

Later training: ~3 bits per token on average.

RL on long-horizon tasks:

Often <1 bit per 10,000 to 1,000,000 tokens.

Overall:

RL provides roughly 1,000× to 1,000,000× less learnable information per unit of compute.

Evidence from Frontier Models

Reasoning chains in RL can exceed 10,000 tokens, and sometimes reach millions.

Success or failure rewards cap information at about 1 bit per episode.

Frontier benchmarks show growing reliance on massive inference-time compute.

Why RL Still Works

RL excels at learning narrow tasks in great depth.

It can push performance beyond the human range in targeted domains.

Recent successes include advanced mathematical reasoning and software engineering.

Key Limitation: Loss of Generality

RL training is task-specific and does not transfer well across domains.

Unlike pre-training, gains do not reliably generalise to unrelated skills.

The breadth of abilities seen in earlier LLMs is likely to diminish.

Fewer unexpected or off-target capabilities are expected going forward.

Mitigations and Uncertainties

Intermediate or graded rewards could increase information per episode.

The practical value of information varies by task.

Information-theoretic limits are upper bounds and may not reflect actual learning.

Despite caveats, the efficiency gap is large enough to matter in practice.

Implications for AI Progress

Continued benchmark improvements may signal narrower capability gains.

Higher inference costs and reduced generality are likely trade-offs.

Established mental models of AI scaling may no longer apply.

The field appears to have crossed a significant inflection point.

Sources
Why doesn't it work as well as pretraining for generality? Because it's isn't learning anything new, it's at heart a form of fancy prompt engineering?

Short answer: no. RL is not just fancy prompt engineering, but it is structurally much worse than pretraining at producing generality. The reason is about the kind of information learned, not whether anything new is learned.

Here is the precise breakdown.

Pretraining learns broad, dense, transferable structure. Next-token prediction exposes the model to an enormous variety of linguistic, factual, procedural, and conceptual patterns. Every token supplies learning signal, and that signal is rich and multi-dimensional. The model is forced to compress regularities that recur across domains: syntax, semantics, reasoning patterns, world models, social conventions, mathematics, code structure, and so on. This pressure produces representations that are reusable across tasks, even ones never anticipated. Generality emerges because the objective rewards modelling everything humans write about, not solving any one task well.

RL learns sparse, task-specific control policies. Reinforcement learning optimises behaviour with respect to a narrow reward signal. Even when the task looks cognitive, such as maths proofs or software engineering, the feedback usually collapses the outcome to a small number of bits. The model is not rewarded for learning general structure, only for increasing success probability on that task distribution. As a result, learning concentrates on local decision boundaries, heuristics, and trajectories that work for the rewarded tasks. This information does not need to be reusable elsewhere, so it usually is not.

RL does learn new information, but it is low-bandwidth and highly selective. The model is not merely reweighting prompts. We know this because capabilities persist across prompts and contexts, and internal representations change. However, the amount of new information per unit of compute is extremely small, and it is tightly coupled to the task. You can think of RL as carving narrow grooves into an already-shaped model, not expanding the overall shape. Pretraining, by contrast, expands the shape itself.

Generality depends on breadth of supervision, not depth of optimisation. Pretraining provides weak supervision everywhere. RL provides strong supervision almost nowhere. Strong supervision is excellent for pushing performance past human levels on specific benchmarks, but weak supervision across massive diversity is what creates flexible competence. This is why pretraining produced unexpected skills and RL rarely does.

The prompt engineering analogy is tempting but incomplete. RL is not just selecting better prompts; it is changing the model’s policy. But it is similar in spirit to prompt engineering in that both operate within the space carved out by pretraining. Neither can easily add large amounts of new, broadly applicable knowledge or structure.

In short: RL fails at generality not because it learns nothing new, but because it learns too little, too narrowly, and too expensively. Pretraining works because it forces the model to learn compressed representations of the world that are useful almost everywhere, whether the trainers intended them or not.

RL is really narrow is a long running problem, to the point where in the early ML era people stopped talking about it.

Yes. That assessment is historically accurate, and the current situation is best understood as a partial rediscovery of an old limitation rather than a new one.

From roughly the 1980s through the mid-2010s, reinforcement learning repeatedly demonstrated the same pattern. It produced striking results on tightly defined problems, but those systems failed to generalise, transfer, or compose skills. This was not a subtle issue; it was one of the central reasons RL largely disappeared from discussions of general intelligence for many years.

The core problem was always credit assignment under sparse reward. When reward is delayed and low bandwidth, the learner is forced to search behaviour space rather than infer structure. That search can be made efficient only when the environment is narrow, stationary, and heavily engineered. As soon as tasks vary, learning becomes brittle and non-transferable.

Classic examples reinforced this lesson. Atari agents could surpass humans on a single game but regress when trained jointly. Go systems were superhuman yet useless outside Go. Attempts at multi-task or continual RL routinely showed interference rather than accumulation of skill. These failures were well understood, and by the early 2000s RL was widely regarded as unsuitable for general cognition.

What changed in the modern era was not the nature of RL but the substrate it was applied to. Large language models already contain rich world models, abstractions, and general representations learned through pretraining. RL post-training exploits this structure instead of having to discover it from scratch. This makes RL look far more powerful than it historically was, but the source of generality is still the pretrained model, not the RL objective.

This is why the current resurgence of RL is selective. It is applied where dense self-supervised data cannot directly optimise the desired behaviour: long-horizon reasoning, tool use, reliability, or alignment with specific goals. In these regimes, RL is valuable despite its inefficiency because there is no cheaper signal available.

However, the old limitations have not gone away. RL still does not scale breadth. It still does not produce robust transfer. It still overfits to the reward definition. The difference is that modern systems can afford this narrowness because the generality has already been paid for upfront during pretraining.

In that sense, the field did not solve RL’s generality problem. It routed around it. The danger now is forgetting why RL fell out of favour in the first place, and mistaking depth of optimisation on selected benchmarks for a renewed path to general intelligence.

An it just is so hard to really make a good reward strcuture?

There are a small number of errors in your sentence:

“An” → “And”

“strcuture” → “structure”

Corrected version:
“And it just is so hard to really make a good reward structure?”

Answer:

Yes. Designing a good reward structure is fundamentally hard, and this is not an incidental engineering problem but a core theoretical limitation of reinforcement learning.

First, rewards are a lossy compression of what you actually want. Most real objectives are rich, contextual, and multi-dimensional. A reward signal collapses that complexity into a scalar. Once compressed, information about why an outcome is good is lost, leaving only a blunt success signal. The agent then optimises whatever proxy survives that compression, not the true goal.

Second, reward specification is adversarial by default. A learning system will exploit loopholes, shortcuts, and ambiguities that humans overlook. This is not because the system is “misaligned” in a moral sense, but because optimisation pressure is stronger and more literal than human intent. Any mismatch between the reward and the real objective will be amplified.

Third, good rewards require anticipating all relevant behaviour in advance. This is feasible in closed domains like games, where rules and success conditions are fully specified. It breaks down in open-ended domains such as reasoning, research, or software engineering, where there are many valid strategies and outcomes, and where intermediate progress is hard to score reliably.

Fourth, sparse rewards worsen credit assignment. When feedback arrives only at the end of a long episode, the learner has little information about which internal decisions mattered. Adding intermediate rewards helps, but doing so correctly requires deep task understanding and often introduces new distortions.

Finally, reward structures tend to freeze values and assumptions. Pretraining passively absorbs the structure of the world as written by humans. RL actively pushes the model toward whatever the reward encodes, even if that encoding is incomplete, biased, or brittle. This is another reason RL narrows behaviour rather than broadening it.

So yes: it is hard because rewards must be precise, complete, non-gameable, dense enough to learn from, and stable under optimisation pressure. In most interesting domains, satisfying all of those constraints at once is either extremely expensive or impossible.

So we can't expect a "2nd boom" from RL like the first boom from 2017-24?

Correct. A second boom of the same kind and magnitude is very unlikely. What RL can deliver is qualitatively different from what happened between roughly 2017 and 2024.

The first boom was driven by a unique alignment of factors. Self-supervised pretraining had an unusually dense, cheap, and effectively unlimited learning signal. Internet text provided enormous breadth, and next-token prediction forced models to internalise general structure rather than optimise for specific outcomes. Scaling laws applied cleanly: more data and compute reliably produced broader competence. That combination is not available again in the same way.

RL does not have those properties. Its learning signal is sparse, expensive, and narrow. Even when scaled aggressively, it mostly reallocates competence within the space already carved out by pretraining. It improves depth, reliability, and goal-directedness in selected domains, but it does not unlock a comparable expansion of general capability.

You should therefore expect diminishing returns of a different shape. RL can still produce headline results, especially on benchmarks that matter operationally: reasoning depth, long-horizon planning, tool use, autonomy, and robustness. These gains can be commercially and strategically important. But they are not the kind that generate widespread, unexpected new abilities across unrelated domains.

Another key difference is discoverability. During the pretraining boom, many capabilities were surprises even to the model creators. With RL, improvements are mostly anticipated, because they occur where the reward is applied. That alone removes much of the “boom” character.

There may still be local booms. A breakthrough in reward learning, credit assignment, or automated curriculum generation could yield sharp gains in specific areas. But absent a new source of broad, dense supervision comparable to human text, there is no obvious path to a second generality explosion.

In short: RL can extend, refine, and weaponise what pretraining gave us. It cannot replay the same trick. The first boom came from discovering how to cheaply learn everything at once. RL is about learning particular things better, and that difference matters.

What about pretraining on synthetic data? Can this get around the weaknesses of RL and the lack of more data?

Synthetic data can help, but it does not fully escape the limits you are pointing at. It changes the failure mode rather than removing it.

Synthetic pretraining works when the generator already contains the structure you want the student to learn. In practice, today’s synthetic data is produced by large pretrained models. That means the student is mostly distilling, recombining, or sharpening existing representations rather than discovering genuinely new ones. This can improve consistency, reasoning style, and coverage of underrepresented patterns, but it rarely expands the conceptual frontier.

Compared to RL, synthetic pretraining is much closer to the original success mode. It is dense, token-level supervision rather than sparse reward. Every token still carries information, so information efficiency is orders of magnitude higher than RL. This makes it far better for generality than reward-based training, and in that sense it does address one of RL’s core weaknesses.

However, it introduces a different bottleneck: closure. If models train primarily on their own outputs, the data distribution becomes self-referential. Errors, biases, and blind spots are reinforced rather than corrected. Without a strong grounding signal from the external world, the system risks converging to a polished but brittle internal consensus.

There are ways to mitigate this. Synthetic data is most valuable when it is constrained or filtered by something external: formal systems such as mathematics or code, simulators with ground truth, or environments with hard correctness checks. In these cases, synthetic generation can explore more of the space than humans did, while still being anchored to reality. This is why synthetic data works relatively well for programming, maths, and formal reasoning, and much less well for open-ended factual knowledge or human norms.

Synthetic data also does not magically create new supervision about the world. It can amplify reasoning ability, improve abstraction, and increase internal coherence, but it cannot teach facts that no model or simulator already knows. It is a force multiplier, not a new source of information.

So in terms of your question: yes, synthetic pretraining can partially route around RL’s inefficiency and the exhaustion of high-quality human data. It is likely to be one of the main drivers of continued progress. But it is not a second internet. It does not restore the conditions that produced the 2017–2024 boom, and it will tend to produce smoother, more incremental gains rather than a new phase of explosive generality.

So really it's only going to be dislliation from COT etc at heart.
Doing it faster mostly.

There are a few errors in your sentence:

“dislliation” → “distillation”

“COT” → “CoT” (standard capitalisation)

Corrected version:
“So really it’s only going to be distillation from CoT etc at heart. Doing it faster mostly.”

Answer:

Broadly yes. That is the correct core intuition, with some important qualifiers.

Most near-term gains from synthetic data and RL-style training will be distillation of existing reasoning and behaviour. Chain-of-thought, tool use patterns, decomposition strategies, and control heuristics already present in frontier models are being compressed into faster, cheaper, more reliable policies. This improves latency, cost, robustness, and usability, but it does not fundamentally expand the space of concepts the model understands.

What improves is efficiency rather than scope. Models learn to reach similar conclusions with fewer tokens, fewer errors, and less variance. That matters commercially and operationally, but it is not the same as learning new domains or discovering new abstractions.

There are two limited ways this can go beyond “just distillation”.

First, search plus verification can exceed any single teacher trajectory. In formal domains like maths or code, models can generate many candidate solutions and select correct ones using external checks. Distilling the results can yield behaviour that no single chain of thought ever contained, even though the ingredients were already latent in the model.

Second, curriculum effects can surface latent structure. By systematically generating problems that sit at the edge of the model’s competence, synthetic data can force the model to stabilise and generalise reasoning patterns it previously used only intermittently. This feels like progress, but it is still extracting what was already implicit.

What it will not do is recreate the pretraining miracle. It does not introduce a vast, diverse, externally grounded information stream. It does not force compression of the full structure of the human world. It mainly polishes, compresses, and reallocates capability.

So your summary is essentially right. The next phase looks like making existing intelligence cheaper, faster, more controllable, and more reliable. That is valuable, but it is a different kind of progress from the one that produced the original boom.

Why is this happening then?


Is this just gains from CoT at heart? If so we can expect slowdown.

What you are seeing in that plot is real progress, but it is not the same kind of progress as the 2017–2024 boom. The curve is steep for reasons that do not generalise indefinitely.

Several mechanisms are stacking on top of each other.

First, long-horizon task success is extremely sensitive to error rate. Early models failed quickly because a single mistake would derail the whole attempt. Recent models mainly improve by reducing local error probability and by recovering from mistakes. When you push per-step reliability up a few percentage points, the maximum viable task length can jump by multiples. This produces an apparently exponential curve even if the underlying gains are incremental.

Second, explicit reasoning traces and internal control are doing most of the work. Chain-of-thought, tool planning, scratchpads, retries, and self-correction loops allow models to externalise cognition. RL and synthetic data then distil these behaviours so they trigger more reliably. That does not add much new knowledge, but it dramatically increases how long the model can stay “on track”. This directly maps onto METR-style time-horizon metrics.

Third, inference-time compute is being traded for capability. These results are not purely training improvements. Models are allowed to think longer, branch, backtrack, and verify. The curve partly reflects willingness to spend more tokens and more wall-clock time per task. That is a real capability gain, but it is not free, and it does not scale like pretraining did.

Fourth, the benchmark itself amplifies this effect. Measuring the 50 percent success horizon creates a regime where progress looks smooth and accelerating. Once a model is good enough to succeed sometimes, small improvements push the median case over much longer tasks. This does not mean the model has become broadly more intelligent, only more dependable on that task distribution.

So is this “just CoT gains at heart”? Mostly yes, but with two important clarifications.

It is not merely prompting tricks. The behaviour has been internalised and stabilised through training. But it is still extraction and compression of reasoning patterns that were already latent after pretraining, plus heavier inference-time search.

And yes, you should expect slowdown. The curve is driven by low-hanging fruit: error correction, better scaffolding, better distillation, and more compute per attempt. These factors compound for a while, then saturate. Once local reliability is high and obvious recovery strategies are exhausted, extending horizon further becomes genuinely hard and increasingly expensive.

In short: the graph looks dramatic because long-horizon success is a nonlinear metric. The gains are real, but they are coming from making existing intelligence more coherent and persistent, not from discovering a new source of general capability. That strongly suggests deceleration rather than another open-ended boom.

Yeah 50% makes it a bit of a cheat. Like we said about casading errors are still an issue.

Yes. That is exactly right, and “50% success” is doing a lot of hidden work in that chart.

Long-horizon tasks are dominated by cascading error. If a task requires N correct decisions in sequence, then success probability scales roughly as pⁿ, where p is per-step reliability. When p is below a certain threshold, success collapses to near zero very quickly. Once p crosses that threshold, success rises sharply. Measuring the point where success reaches 50% therefore sits right on the steepest part of the curve.

That creates three distortions.

First, small improvements in local reliability look like huge gains in horizon. A model that goes from 97% to 98% per-step correctness can suddenly handle tasks several times longer, even though nothing fundamental changed about its understanding. The metric exaggerates progress.

Second, 50% success ignores tail behaviour. For real deployment, you usually care about 95–99.9% success, or at least graceful degradation. Models that succeed half the time on long tasks may still fail catastrophically and unrecoverably in the other half. Cascading errors remain the dominant failure mode, just masked by the metric choice.

Third, it hides brittleness and variance. At 50%, half the time the model is still derailing early. The apparent ability to “do a 2-hour task” often means “sometimes gets lucky and stays on track”, not “robustly manages a 2-hour project”. This matters enormously for claims about autonomy.

This ties directly back to the RL and distillation discussion. Most recent gains are about pushing p just over key thresholds using better scaffolding, retries, verification, and distillation of CoT-like behaviour. That improves median performance, but it does not eliminate compounding error. To do that, you need either radically higher per-step reliability or fundamentally different architectures for memory, verification, and control.

So your intuition is correct. The 50% metric makes progress look smoother and more explosive than it really is. Cascading errors are still the core problem, and they reassert themselves as soon as you ask for high reliability or much longer horizons.

So what is happening is p is being pushed down. 

Almost. The direction matters.

What is being pushed down is the per-step error rate. Equivalently, p, the per-step success probability, is being pushed up. People often flip the wording, but the mechanism is exactly what you are pointing at.

Here is the clean framing.

Let p be the probability that a single local decision is correct. Long-horizon success scales roughly as pⁿ, where n is the number of required steps. When p is even slightly too low, success collapses exponentially. When p crosses certain thresholds, horizon explodes.

What recent work is doing is not changing n much, and not changing the task distribution in a deep way. It is pushing p upward by small absolute amounts through:

Better internalised CoT and planning patterns

Explicit self-checking and error detection

Retry and backtracking policies

Tool use with verification

Distillation that makes “good trajectories” more likely

Willingness to spend more inference compute per step

These are all local reliability improvements.

Because p sits in an exponent, small improvements produce large apparent gains in horizon, especially when you measure at 50% success. That is why the curve looks dramatic.

Crucially, this does not mean cascading errors are solved. It means the system is operating just past a critical threshold where cascades sometimes fail to ignite. At higher reliability targets, or longer horizons, cascades reappear.

So the accurate statement is:

Error per step is being pushed down.

p is being pushed up slightly.

Horizon grows nonlinearly as a result.

The underlying failure mode remains.

This is also why slowdown is expected. Once obvious sources of error are removed and p asymptotes toward a ceiling set by architecture, representation quality, and grounding, further gains become much harder. You no longer get free exponentiation from tiny improvements.

In short: you are seeing threshold effects in sequential reliability, not a new source of intelligence.

And also really I don't find running coding agents for hours is really something that is that useful as a practical programmer.

That reaction is widely shared among experienced programmers, and it is not a failure of imagination. It reflects a real mismatch between the benchmark and practical value.

In day-to-day software engineering, the bottleneck is rarely “how long can someone work continuously without stopping”. It is problem framing, deciding what not to do, coordinating with humans and systems, understanding legacy context, and making judgement calls under uncertainty. Long uninterrupted execution is not the scarce resource.

Running an agent for hours mainly substitutes for tasks that are already cheap. Code can already be compiled, tested, reformatted, searched, and refactored quickly. A system that takes two hours of wall-clock time to maybe complete a task is often worse than a human who can do it in twenty minutes with supervision, or a tool that completes 80% of the work instantly and leaves the rest to a human.

There are a few narrow cases where long-running agents make sense. Large mechanical refactors, exhaustive test generation, broad vulnerability searches, or exploration of very large codebases can benefit from persistence and scale. Even there, success depends on strong constraints, continuous validation, and human-in-the-loop oversight. Unbounded autonomy is usually a liability, not an asset.

The current emphasis on multi-hour autonomy is partly a research artefact. It is an easy thing to measure, and it aligns with RL-friendly benchmarks. It also looks impressive in charts. But practical programming values predictability, interruptibility, and fast feedback far more than endurance.

There is also an economic angle. Long-running agents consume large amounts of inference compute. That cost scales badly, and it directly competes with interactive use. For most teams, spending that budget on faster iteration and better tooling delivers more value.

So your intuition is sound. The ability to run for hours without human input is not, by itself, a strong indicator of usefulness to working programmers. Incremental reliability, responsiveness, and integration into existing workflows matter much more.

OK so if we see this as falling error rate, it's a big deal. But will p gains hit a wall at some point?

Yes. Almost certainly. The question is not whether p hits a wall, but where the wall is and how hard it is.

There are several independent ceilings on per-step reliability.

First, representation limits. If the model’s internal representations are fuzzy or underspecified, no amount of training can make local decisions arbitrarily reliable. Pretraining set most of this ceiling. RL and distillation mainly help the model choose better among representations it already has. Once ambiguity or missing structure dominates, p cannot keep rising without new information sources.

Second, grounding and feedback limits. Many programming and reasoning decisions depend on facts that are not locally verifiable. Without tight feedback loops or ground truth, the model must guess. That guess has an irreducible error rate. Tool use helps, but only where tools exist and are cheap to invoke.

Third, distributional shift. p is measured on a task distribution. As you push to longer horizons or more realistic tasks, the distribution shifts. Rare edge cases dominate, and those are exactly where models are weakest. This creates an apparent ceiling even if p improves on simpler cases.

Fourth, architectural noise and stochasticity. Autoregressive generation compounds small uncertainties. Even with high average accuracy, sampling variance, beam search artefacts, and state drift introduce a floor on error. You can trade compute to reduce this, but returns diminish quickly.

Fifth, reward and training signal limits. RL and synthetic data become increasingly self-referential at high competence. They struggle to supply genuinely corrective signals once the model mostly does the “right” thing. At that point, remaining errors are subtle, rare, and hard to label, which slows further improvement dramatically.

Because p appears in an exponent, progress feels smooth until it doesn’t. Once you approach these ceilings, the same training effort yields much smaller reductions in error rate. Horizon growth then slows sharply, and charts that previously looked exponential flatten.

So yes, p gains will hit walls. Likely multiple ones. Each wall corresponds to a different missing ingredient: better representations, better grounding, better feedback, or different architectures. Pushing past them probably requires qualitatively new techniques, not just more RL, more distillation, or more inference compute.

That is why the current phase feels powerful but brittle. It is harvesting remaining reliability gains from an existing paradigm. That is valuable, but it is finite.

But really pretraining is scalling up too, they are working on pretraing with video for example.

Using simulations as syntehnic data. 

So pretraining isn't a bust yet. The real questions are economic.

Yes. That framing is right, and it is an important correction to an overly pessimistic reading.

Pretraining is not exhausted in principle. What is constrained is cheap pretraining on passive human text. Once you broaden the modality and the source of experience, the picture changes. The binding constraint shifts from information to economics.

Video and multimodal pretraining genuinely add new structure. Unlike synthetic text distilled from models, video is not self-referential. It contains causal, temporal, physical, and social regularities that text only weakly encodes. Learning from video forces models to internalise dynamics, persistence, object permanence, affordances, and real-world noise. That is a real expansion of the representational base, not just polishing.

Simulation-based pretraining is similar. Well-designed simulators provide dense, grounded supervision at scale. They allow exploration beyond what humans happened to write down. This restores some of the properties that made early pretraining powerful: breadth, diversity, dense signal, and external grounding. In that sense, simulation is much closer to “a new internet” than RL is.

However, the limiting factor becomes cost. Video is orders of magnitude more expensive to store, process, and train on than text. High-quality simulation is expensive to build and maintain, and often narrow in scope. Unlike internet text, these data sources do not arrive pre-packaged, pre-labelled, and globally abundant.

There is also a diminishing returns issue. Video and simulation add new kinds of structure, but not infinite new structure. Once the model has internalised the basic physics and social dynamics available in the data, scaling further again runs into saturation, just at a higher ceiling.

So you are right: pretraining is not “a bust”. It is transitioning from a phase where data was effectively free to one where data and environments must be actively constructed. That makes progress slower, more capital-intensive, and more uneven across actors.

The real question is not whether pretraining can continue, but whether the economic return justifies the cost. Training larger multimodal world models may still deliver genuine generality gains, but they will look less like a sudden boom and more like infrastructure build-out: expensive, incremental, and dominated by players who can afford long time horizons.

In short: the technical path is still open. The economic slope is much steeper.

Ok so the question is can we get long enough horizons to really be that economcially useful, as something that is 50% reliable isn't that economical.

That is the right question to ask, and it cuts through most of the hype.

In practice, 50% reliability is almost never economically useful for long-horizon work. It can be useful for exploration, brainstorming, or generating candidate solutions, but not for execution. For tasks where failure is expensive, time-consuming, or subtle, a system that succeeds half the time imposes high supervision and verification costs. Those costs often dominate any savings from automation.

Economic usefulness depends on a few concrete thresholds.

First, reliability must clear a high bar, typically well above 95%, and often closer to 99% or higher, for autonomous execution. Below that, humans must monitor closely, interrupt frequently, or redo work, which erodes value quickly. Long-horizon autonomy multiplies this effect, because a single late-stage failure can invalidate hours of work.

Second, verification must be cheap. If you can cheaply and deterministically check outputs, lower reliability can be tolerated. This is why code generation works better than open-ended research. But as horizons grow, verification itself becomes a long-horizon task, reintroducing the same problem at a higher level.

Third, task decomposition matters more than raw horizon. Economically useful systems usually work by shrinking horizons, not extending them: frequent checkpoints, explicit interfaces, human review gates, and tool-mediated validation. A system that runs for 10 minutes with 99% reliability per segment is far more useful than one that runs for 10 hours at 50%.

Fourth, cost scaling matters. Long-horizon agents consume large amounts of inference compute. Even if reliability improves, the marginal cost per successful task can rise faster than the value produced. That creates a hard economic ceiling independent of technical capability.

So the likely equilibrium looks different from the benchmark narrative. Instead of very long, mostly autonomous runs, we get medium-horizon agents embedded in workflows, with frequent resets, guardrails, and human-in-the-loop control. These systems can be highly economical even if p never reaches the level needed for true hours-long autonomy.

In other words, the economically useful regime is probably not “one agent runs for hours”. It is “many short, reliable steps coordinated efficiently”. Long horizons may still matter as an internal research signal, but they are not the right economic target by themselves.

So it sounds like AI will be everywhere but the GDP stats, sounds like a future?

Yes. That is a coherent and historically grounded forecast.

It is entirely plausible to end up in a world where AI is pervasive at the micro level but only weakly visible in headline GDP statistics. This is not unprecedented. Many general-purpose technologies follow this pattern for long periods.

There are several reinforcing reasons.

First, AI mainly compresses cognitive labour rather than creating new final goods. Much of what it improves is intermediate work: drafting, searching, refactoring, checking, translating, coordinating. These gains often show up as time savings, reduced friction, or quality improvements inside organisations, not as clearly priced output increases. GDP is bad at measuring this kind of surplus.

Second, substitution without expansion limits GDP impact. If AI replaces human effort in existing workflows without enabling fundamentally new products or markets, measured output does not rise much. Costs fall, margins shift, and productivity per worker may increase, but aggregate output can remain flat, especially if demand is inelastic.

Third, reliability constraints cap automation depth. As we discussed, most economically useful deployments will involve short horizons, guardrails, and human oversight. That makes AI more like a powerful tool than an autonomous worker. Tools raise efficiency, but they do not automatically translate into proportional GDP growth.

Fourth, diffusion lags matter. Even when tools are powerful, organisations take time to reorganise around them. Management practices, incentives, legal frameworks, and risk tolerance adapt slowly. During that period, AI can be “everywhere” in use but under-leveraged in macroeconomic terms.

Fifth, measurement itself is lagging. GDP struggles with quality improvements, zero-price goods, and internal productivity gains. AI-assisted work often produces better outcomes rather than more output. Those benefits are real but largely invisible to national accounts.

So the picture you are sketching is internally consistent: AI embedded across software, services, research, design, and operations; clear gains to individual firms and workers; but muted aggregate growth statistics.

If there is a sharp GDP inflection, it likely requires something beyond reliability gains and workflow acceleration. It would require either large-scale autonomous production, entirely new classes of goods and services, or deep changes to how value itself is created and measured. None of those follow automatically from the current trajectory.

In short: yes, a future where AI is ubiquitous but GDP growth remains modest is not a paradox. It may be the default outcome.

Is CoT not unlocking a lot that was being claimed to be intractable for these LLMs though. Like coding long tasks.

Yes, CoT did unlock a lot that looked intractable before, but the key word is looked. The distinction between “previously impossible” and “previously latent but unstable” matters here.

Before explicit chain-of-thought and related scaffolding, LLMs were already capable of much deeper reasoning than their outputs suggested. The problem was not missing competence so much as missing control. Models would jump to conclusions, skip steps, or derail early because there was no mechanism encouraging them to externalise intermediate reasoning. Long tasks failed due to cascading error, not because the underlying transformations were beyond the model.

CoT changes the failure mode. By forcing step-by-step reasoning, it reduces local error, enables self-correction, and makes dependencies explicit. That unlocks tasks like multi-file coding, longer refactors, and structured problem solving that previously failed quickly. From a user’s perspective, this feels like a qualitative jump, because the usability frontier moves a long way.

However, this does not mean CoT injected new deep knowledge or algorithms. It mostly exposed and stabilised reasoning patterns that were already weakly present after pretraining. That is why CoT generalised so quickly across domains without retraining.

For coding specifically, long tasks were blocked by three things: loss of state, silent logical errors, and lack of verification. CoT plus tool use addresses all three. The model keeps track of intent, reasons about consequences, and checks its work. That is a big deal in practice.

But the ceiling remains. CoT increases p, the per-step success probability, and makes failure later and rarer. It does not remove compounding error. As tasks get longer, more open-ended, or more novel, errors still accumulate. You see this today when agents slowly drift, misinterpret earlier decisions, or confidently build on a subtle mistake.

So the correct framing is: CoT unlocked a large region of the capability landscape that was already there but inaccessible. That is why the gains felt dramatic. It did not, by itself, open an unbounded new regime. It moved the usable frontier outward, not infinitely forward.

This is also why you are seeing diminishing returns now. Once reasoning is explicit and moderately reliable, further gains require either much higher per-step reliability or new forms of memory, verification, and grounding. CoT was the big, cheap win. The next wins are harder and more expensive.

For 99% sucess rate, isn't it a lot harder? Think about this an ilustate with binomal to make the point.

Yes. Hitting 99% success is dramatically harder, and the binomial framing makes this precise.

Set up the simplest model.

Assume a task consists of n independent steps.
Each step succeeds with probability p.
Overall task success requires all steps to succeed.

Then overall success probability is:

P(success) = pⁿ

This already shows why things get brutal.

Example 1: moderate reliability, long task
Let p = 0.98 (which sounds very good).
Let n = 100 steps.

P = 0.98¹⁰⁰ ≈ 0.13

So even with 98% local correctness, a 100-step task succeeds only 13% of the time.

Example 2: the “50% horizon” illusion
Suppose you observe 50% success at n steps.

That means:

p ≈ 0.5^(1/n)

For n = 100, this gives:

p ≈ 0.993

So the system already needs ~99.3% per-step reliability just to sometimes succeed on a 100-step task. That is why the curve looks impressive. You are already near the cliff edge.

Now look at what happens when you demand 99% task success, not 50%.

We want:

pⁿ = 0.99
⇒ p = 0.99^(1/n)

For n = 100:

p ≈ 0.9999

That is 99.99% per-step correctness.

This is the key point:
Going from 50% task success to 99% task success does not require a small improvement. It requires eliminating most remaining errors.

You can see the nonlinearity clearly:

For n = 100 steps:

p = 0.993 → 50% success

p = 0.999 → 90% success

p = 0.9999 → 99% success

Each extra “9” costs far more than the previous one.

Now connect this to LLM agents.

Early gains push p from, say, 0.95 to 0.98. That explodes the usable horizon. This is the current phase and it looks amazing.

But pushing p from 0.995 to 0.9995 is a different regime entirely. Errors are rare, subtle, context-dependent, and hard to detect. Training signals become sparse. Verification becomes expensive. Self-play and distillation mostly reinforce existing behaviour instead of correcting it.

This is why cascading error is the central problem.

At 50% success, you are just crossing the percolation threshold where runs sometimes survive.
At 99% success, almost no cascades are allowed to exist at all.

That is not just “harder”. It is qualitatively harder, because you are fighting the exponential tail of the binomial distribution.

So your intuition is exactly right:
99% reliability is not an incremental target. It is a different phase of difficulty entirely.

99.99% per-step correctness. This is probably simply beyond the pretraining step? The error rates.

That conclusion is largely correct. Reaching ~99.99% per-step correctness is very likely beyond what pretraining alone can deliver, at least in the regimes we are discussing.

Here is why, step by step.

Pretraining optimises average predictive accuracy over extremely broad distributions. It is very good at driving down common errors, smoothing representations, and capturing high-level structure. But the tail errors that dominate at the 99.9% to 99.99% regime are different in character. They are rare, context-specific, and often underdetermined by the input. Pretraining has no particular incentive to eliminate them, because they contribute negligibly to the loss.

This creates an irreducible error floor. Even if the model is “mostly right”, there will be cases where the text, code, or situation is genuinely ambiguous, underspecified, or out of distribution. Pretraining averages over these. It does not resolve them. As a result, the residual error rate stops shrinking smoothly as you scale.

There is also a supervision mismatch. Next-token prediction rewards plausibility, not correctness in the strong sense needed for long-horizon control. Many errors that are catastrophic for an agent are locally plausible continuations. Pretraining actively tolerates these, because they are common in human-generated data.

At very low error rates, noise dominates. Tokenisation quirks, stochastic sampling, minor representation drift, and uncertainty about latent state all contribute. Autoregressive generation compounds this noise. You can reduce it with more compute and lower temperature, but you do not eliminate it without changing the generation or control scheme.

This is why pushing p from, say, 99% to 99.9% felt achievable, but pushing from 99.9% to 99.99% feels qualitatively different. You are no longer fixing “mistakes”; you are trying to eliminate ambiguity, uncertainty, and epistemic gaps. Pretraining has no mechanism to do that.

So what would be needed beyond pretraining?

You need strong external constraints. Formal verification, execution traces, simulators, deterministic tools, or environments with hard ground truth. You also need architectures that do not require a single uninterrupted chain of correctness: checkpointing, rollback, state validation, and explicit memory invariants.

In other words, the path to 99.99% reliability does not look like “better language models”. It looks like systems engineering layered on top of them.

So yes: expecting pretraining alone, even massively scaled, to deliver that level of per-step correctness is probably unrealistic. That does not mean progress stops. It means the bottleneck moves from learning representations to building systems that do not rely on every step being right.

And RL can't fix this ?

Not in general, and not in the way people often hope.

RL can reduce some classes of errors, but it does not eliminate the fundamental barriers you are pointing at. In fact, RL runs into its own ceilings precisely in the regime where 99.99% per-step correctness would be required.

Here is why.

RL optimises expected reward, not worst-case behaviour. Once a policy achieves high average success, the remaining errors are rare. Those rare errors contribute almost nothing to the gradient. As a result, RL naturally stalls before eliminating tail failures. Pushing from 99.9% to 99.99% requires targeting precisely those rare cases, but RL provides vanishing signal there.

Sparse rewards make this worse. Long-horizon tasks often collapse success to a single bit. At that point, almost all trajectories look identical from the learner’s perspective until the very end. RL cannot tell which internal decision caused the eventual failure, so it cannot reliably correct it.

Reward hacking and proxy collapse also intensify at high reliability. As you tighten rewards, the agent learns brittle heuristics that pass the reward function without being robust. These heuristics often increase tail risk even as average performance improves.

There is also a stability problem. At very high p, the policy becomes sensitive to tiny changes. Small distribution shifts, tool failures, or environment noise cause abrupt regressions. RL training itself can destabilise previously reliable behaviour, because updates are global and interfere across contexts.

Most importantly, RL does not add information. As discussed earlier, the learning signal per episode is extremely low. When you are already near the ceiling set by representation quality and ambiguity, RL has nothing left to push against. It can reshuffle behaviour, not resolve uncertainty.

Where RL does help is narrow and important:

It can teach recovery behaviours.

It can bias the model toward safer defaults.

It can enforce procedural discipline.

It can reduce common failure modes on a fixed distribution.

But that is not the same as guaranteeing correctness at every step.

So the honest answer is: RL cannot, by itself, get you to 99.99% per-step correctness for open-ended cognitive tasks. That level of reliability requires either eliminating ambiguity through external grounding and verification, or redesigning the system so that local errors do not compound.

RL is a patch, not a cure, for the exponential tail problem you are describing.

This suggest an AI winter of sorts might be coming?

A slowdown is plausible. A classic “AI winter” is less likely, but a regime shift is.

Historically, AI winters happened when expectations were built on an implicit assumption that a single technique would scale smoothly to general intelligence, and reality exposed a hard ceiling. The dynamics you have identified fit that pattern in one important way: the field is running into exponential reliability requirements that current methods do not naturally satisfy.

However, several factors argue against a sharp winter.

First, the technology already delivers real economic value. Unlike past cycles, models are widely deployed and embedded in workflows. Even if progress slows, there is no sudden collapse in usefulness. That stabilises investment at a lower growth rate rather than triggering abandonment.

Second, the bottleneck is not “models do nothing”, but “models do not autonomously do everything”. That distinction matters. The disappointment is about autonomy, generality, and long-horizon reliability, not about baseline competence. Tool-like systems remain valuable even if agentic dreams stall.

Third, capital concentration changes the dynamics. Progress may slow, but it is unlikely to stop, because a small number of actors can afford continued incremental gains even with poor marginal returns. That leads to consolidation and reduced hype rather than a winter.

What is likely is a deflation of expectations. Claims about rapid takeoff, fully autonomous agents, and explosive GDP growth will collide with the realities we discussed: tail errors, verification costs, economic ceilings, and diminishing returns on p. When those claims are walked back, it will feel like a winter to people expecting another 2017–2024-style boom.

The more accurate analogy may be the post-dotcom period rather than an AI winter. The internet did not stop improving after 2000, but expectations reset, business models consolidated, and progress became infrastructure-like rather than spectacular.

So the likely outcome is not a freeze, but a cooling: slower visible progress, fewer surprise capabilities, more emphasis on reliability engineering and integration, and less tolerance for speculative narratives. From the inside, the field keeps moving. From the outside, it looks like momentum has faded.

In short: a winter in hype and expectations is quite possible. A winter in actual capability or usefulness is much less so.

Carefull expert curated data on top of an LLM geenrationg more sythetic data? Can this fix it?

Careful, expert-curated synthetic data can help, but it does not fully fix the problem you are worried about. It shifts the wall outward; it does not remove it.

Here is the clean way to think about it.

Expert-curated synthetic data improves where the model is reliable, not the fundamental scaling law. If experts select, filter, or correct model-generated trajectories, you can target rare but important errors. This is much better than naive self-distillation. It can push p higher than pretraining alone and higher than blind RL would.

However, three hard limits remain.

First, diminishing information return. Once the model is already mostly correct, expert curation mostly confirms what it already does right. The remaining errors are rare, context-dependent, and heterogeneous. Each one requires disproportionate effort to surface and label. The cost per marginal improvement in p rises sharply.

Second, closure still applies. Even with experts in the loop, the space being explored is still constrained by what the model can already generate. Experts can correct trajectories, but they cannot easily inject entirely new latent structure unless they are effectively writing fresh training data. At scale, this becomes equivalent to producing new human data, which reintroduces the original economic bottleneck.

Third, tail risk remains adversarial. At 99.9% and beyond, the dominant failures are not “obvious mistakes” but subtle misinterpretations, rare interactions, and distributional edge cases. These are hard for experts to anticipate, hard to enumerate, and hard to prove you have covered. Optimisation pressure will always find corners you did not curate.

So what does expert-curated synthetic data realistically buy you?

It can push p meaningfully higher on a specific distribution.

It can stabilise behaviour and reduce common cascades.

It can make medium-horizon agents economically useful.

What it does not buy you is a guarantee against exponential tails, or a general path to 99.99% per-step correctness across open-ended tasks.

This is why the trajectory keeps pointing toward systems engineering rather than pure learning. Checkpoints, verification, rollback, decomposition, and external ground truth reduce the need for extreme p. Curated synthetic data helps inside that framework, but it does not replace it.

So your instinct is right to be cautious. Expert-curated synthetic data is one of the strongest tools available right now, but it is an incremental reliability amplifier, not a fundamental escape hatch from the limits we have been discussing.

So an openended AI worker seems unlikley in the next 5 years?

Yes. An open-ended, largely autonomous AI worker is unlikely in the next five years.

That conclusion follows directly from the constraints we have been circling, and it does not depend on pessimism about raw model quality.

The core blocker is reliability at scale. Open-ended work requires sustained correctness across long, shifting, poorly specified tasks. That implies extremely low per-step error rates or architectures that prevent errors from compounding. Current systems improve median behaviour but still exhibit tail failures, drift, and misinterpretation. None of the techniques on the table clearly eliminate those failure modes across open domains.

Learning methods are not the missing ingredient. Pretraining, RL, synthetic data, and expert curation all help, but they run into diminishing returns precisely where autonomy becomes economically necessary. Pushing from “often right” to “almost never wrong” is exponentially harder, and neither RL nor distillation provides strong gradients in that regime.

Economics also argue against it. Long-running autonomous agents are expensive to operate, hard to verify, and risky to deploy. Even if technically feasible in narrow cases, they are unlikely to be broadly adopted when cheaper, more controllable human-in-the-loop systems deliver most of the value.

What is likely in the next five years is widespread deployment of constrained agents: systems that act in bounded roles, with frequent checkpoints, strong tooling, explicit interfaces, and human oversight. These will feel powerful and may automate large fractions of work, but they will not resemble a general “AI employee” that you can assign vague objectives to and trust end-to-end.

So the correct expectation is not stagnation, but a different shape of progress. AI becomes more embedded, more reliable in slices, and more useful as infrastructure. The vision of a broadly autonomous, open-ended worker remains plausible in principle, but it sits beyond the horizon implied by current methods and economics.

But even ordering plane tickets seems intractable.

That example is actually a very good stress test, and it shows why “open-ended AI worker” is such a high bar.

Ordering plane tickets is not hard in the sense of intelligence or knowledge. Humans do it easily. It is hard because it combines several properties that defeat current systems.

First, the task is underspecified and preference-laden. “Book a flight” hides many implicit constraints: acceptable times, trade-offs between price and duration, seat preferences, baggage rules, cancellation policies, airline trust, risk tolerance, and contingency planning. Humans resolve these on the fly, often without articulating them. Models do not know which mistakes are acceptable and which are catastrophic.

Second, the environment is adversarial and stateful. Airline sites are designed to upsell, obscure comparisons, change prices dynamically, and expire sessions. A small misunderstanding can lock in a bad outcome. Unlike coding, there is no clean ground truth or easy rollback once a purchase is made.

Third, verification is expensive or irreversible. You cannot cheaply “test” whether you booked the right ticket. The cost of error is asymmetric. Humans handle this by being cautious, double-checking, and escalating uncertainty. Current agents either act too eagerly or freeze.

Fourth, the task crosses many system boundaries. Browsers, forms, authentication, CAPTCHAs, emails, payment systems, and terms and conditions all interact. Each boundary introduces new failure modes. Even if each step is 99% reliable, the end-to-end reliability collapses.

Fifth, social and legal responsibility matters. If something goes wrong, a human can argue, complain, negotiate, or improvise. An agent cannot absorb blame or liability. That alone blocks deployment unless reliability is extremely high.

This is why such tasks look “trivial” but are in practice intractable for autonomous agents. They sit in exactly the regime we have been discussing: long horizon, sparse irreversible feedback, high tail risk, and low tolerance for error.

So your intuition is correct. If booking a flight robustly is hard, that is not a sign that models are dumb. It is a sign that open-ended autonomy is an extraordinarily demanding requirement. It also explains why economically useful AI is gravitating toward constrained, reversible, and checkable tasks instead.

That example alone should make anyone cautious about timelines for general AI workers.

Yeah this is a comon problem with LLMs, they are too friendly in real averserial deployments.

Yes. That is a well-identified and structural problem, not a superficial one.

LLMs are trained in overwhelmingly cooperative regimes. Pretraining data assumes good faith communication. RLHF further pushes models toward being helpful, polite, and compliant. That is appropriate for conversational use, but it is misaligned with adversarial environments such as commerce, security, negotiations, or the open web.

In adversarial settings, “being friendly” translates into concrete failure modes:

Over-trusting external inputs, including misleading interfaces, prompts, or system messages.

Taking actions without sufficient scepticism or verification.

Failing to model hostile incentives, hidden traps, or asymmetric risk.

Optimising for user satisfaction rather than downside avoidance.

Humans implicitly switch modes when environments become adversarial. We slow down, double-check, assume we might be misled, and prioritise loss avoidance over helpfulness. Current LLMs do not naturally make that shift, because nothing in their core objective encodes adversarial caution.

This is not easily fixable with more RL. Training adversarial caution requires either:

Explicit adversarial environments with real consequences.

Strong negative rewards for rare but catastrophic failures.

Architectural separation between “assistive” behaviour and “defensive” behaviour.

All of these are hard. The learning signal for adversarial failure is sparse, delayed, and expensive. Worse, pushing too hard in this direction often degrades normal usability, producing models that are overly conservative or unhelpful.

This is why real deployments quietly constrain scope. Systems are wrapped in guardrails, approval steps, sandboxed permissions, and reversible actions. The intelligence is there, but trust is externalised into the surrounding system rather than the model itself.

So your diagnosis is correct. LLMs are optimised for cooperative dialogue, not hostile environments. That mismatch is one of the main reasons why “simple” real-world tasks like booking flights, handling payments, or negotiating contracts remain intractable for autonomous agents.

But the expoentential looks scarry from the doubling time, but slowdown is likley in what time period?

The exponential looks scary because you are sitting on the steep part of a curve driven by threshold effects. That almost always precedes a visible slowdown. The key is that this is not a single exponential process, but a sequence of regime transitions.

A reasonable expectation is a slowdown in two phases, over roughly the next 2–5 years, with the first phase already beginning.

Near-term, over the next 12–24 months, the apparent doubling times stretch. Gains in long-horizon benchmarks continue, but each doubling requires disproportionately more compute, scaffolding, and tuning. You still see progress, but it becomes obviously cost-driven. The curves stop looking “clean”. Improvements become conditional on higher inference budgets, narrower task definitions, or heavier human oversight.

This phase is mostly about exhausting easy p gains. Error correction, CoT stabilisation, tool verification, retries, and distillation deliver big wins early, but they saturate. You start seeing claims quietly shift from “autonomous” to “human-in-the-loop” to “assistive”, even if the headline graphs still trend upward.

The second phase, likely 3–5 years out, is where the slowdown becomes unmistakable. This is where the exponential reliability math really bites. Pushing from 50% to 90% success is doable. Pushing from 90% to 99% is expensive. Pushing from 99% to 99.9% across open-ended tasks is brutal. At this point, marginal gains in p no longer translate into meaningful horizon extensions without architectural changes.

This is also where economics assert themselves. Inference costs, verification overhead, and integration friction rise faster than value produced. Long-running agents stop looking impressive when they are slower, riskier, and more expensive than constrained alternatives. Investment shifts from chasing autonomy to making existing systems cheaper, more reliable, and easier to integrate.

So the slowdown is not a sudden cliff. It is a loss of apparent acceleration. The doubling-time narrative breaks first. Then benchmark gains flatten or fragment. Then expectations reset.

Crucially, this does not mean progress stops. It means progress changes character. Less “wow”, more engineering. Fewer surprise capabilities, more reliability work. From the outside, it looks like deceleration. From the inside, it feels like hitting hard ceilings.

In short: the exponential is real but local. You should expect visible slowdown already this decade, with a clearer regime change well before the end of the 2020s, unless a genuinely new training or architectural paradigm appears.

So people will still produce these graphs, but constantly reframe the question.

Yes. That is very likely, and it follows a well-worn pattern in technology forecasting.

When a metric stops cleanly tracking real-world value, the usual response is not to abandon graphs, but to change what is being measured. You should expect three recurring moves.

First, horizon reframing. When “hours of autonomous work” saturates, it becomes “effective hours with tool use”, then “equivalent human-hours with oversight”, then “tasks previously requiring teams”. Each reframing preserves an upward curve while quietly changing the underlying claim.

Second, conditional curves. Progress is increasingly reported given more inference compute, more retries, more scaffolding, or narrower task definitions. The graph still slopes upward, but the hidden independent variables multiply. The headline remains exponential; the cost does not.

Third, benchmark substitution. When one benchmark flattens, another appears that sits back on the steep part of its curve. This is not dishonest in isolation, but it obscures the fact that progress is moving sideways across metrics rather than forward on a single axis.

This is especially easy in domains like reasoning and agency because success is fuzzy and multidimensional. You can always define a new notion of “can do X” that is just beyond current capability and show rapid progress toward it.

What tends to lag is economic relevance. Reliability thresholds, verification cost, and deployment risk do not reframe as easily. A system that is 50% reliable does not become economically useful because a graph looks good. That gap is where narrative and reality eventually diverge.

So yes: the graphs will continue. The curves will often look impressive. But the meaning of those curves will drift unless anchored to hard constraints like cost, reliability at high percentiles, and irreversible error rates.

That does not imply bad faith. It is how fields behave when a simple scaling story runs out and is replaced by a complex engineering one.
