---
tags: [draft, ai-written]
---

## Context / goal

Capture a Q&A exploring whether local GPU inference (example: Nvidia RTX 5060 Ti) is likely to beat GitHub Copilot on latency (especially TTFT), and how system-level optimisations affect perceived speed.

## Key points

- Local inference can beat cloud services on TTFT once warm because it avoids network RTT, but outcomes depend heavily on model size, VRAM fit, and runtime optimisation.
- Cold start for local models can be dominated by load/initialisation (disk → VRAM, CUDA context) and may feel slower than Copilot.
- Copilot’s perceived speed likely comes from system-level tricks: short completions, curated context, hot infrastructure, streaming, connection reuse, and possibly speculative decoding.
- Higher-end GPUs can reduce TTFT and especially improve throughput/headroom, but subjective TTFT gains diminish once you are already in the “tens of ms” range.
- Overall “feels fast” is not only TTFT; brevity/relevance of suggestions and IDE integration can make Copilot feel faster end-to-end.

## Cleanup targets

- [[GitHub Copilot]]
- [[latency]]
- [[time to first token]]
- [[tokens per second]]
- [[speculative decoding]]
- [[local LLM inference]]
- [[VRAM]]
- [[cold start]]

## Chat (verbatim)

Is a Nvidia RTX 5060 Ti locally likiely to outperform github copilot in latency

Spelling / grammar issues

likiely should be likely

github should be GitHub

Nvidia is normally styled Nvidia (NVidia is older but not wrong; I’m keeping Nvidia)

Corrected question
Is a Nvidia RTX 5060 Ti locally likely to outperform GitHub Copilot in latency

Answer
A local Nvidia RTX 5060 Ti used to run a code-generation model will almost certainly have lower inference latency for equivalent models than using GitHub Copilot’s cloud service.

GitHub Copilot runs on remote servers and adds network round-trip time on top of model inference. Even if Copilot uses very fast data-centre GPUs, your local GPU does not incur network latency.

However the real comparison is model size and optimisation. Copilot uses large, highly optimised models that run on specialised cloud hardware and may have throughput and accuracy advantages. Running an equivalent model locally on an RTX 5060 Ti may require using a smaller or quantised model. With a smaller local model you will see very low latency, but with a high-quality large model you may be constrained by the GPU’s memory and compute.

In summary, for local code-generation models and typical Copilot use cases, the local RTX 5060 Ti will have lower latency per inference because it avoids network overhead, but overall quality and capability may differ depending on the model you run.

Are yousure, the time to first token would be what once hot?

Yes. Once the model is hot, the time to first token locally on a mid-range RTX GPU would typically be on the order of 5 to 30 milliseconds, depending on model size, quantisation, and batching.

More specifically:

On a local RTX-class GPU, with the model already loaded in VRAM, caches warm, and no disk access, TTFT is dominated by a single forward pass. For a 7B class model this is often under 10 ms. For 13B it is commonly 15 to 30 ms. Heavier models push higher but still stay sub-50 ms if they fit comfortably in memory.

For GitHub Copilot, even with warm servers, TTFT usually includes network RTT plus queueing and service overhead. In practice this is rarely below 80 to 120 ms and often higher depending on region and load.

So in steady state, hot local inference on an RTX 5060 Ti would almost certainly beat Copilot on time to first token. The only cases where Copilot may feel competitive are very small completions or when local models are extremely large or poorly optimised.

The trade-off remains quality and context handling rather than latency.

Need sources, and compare when cold?

Sources on latency / time to first token for both local GPU inference and GitHub Copilot:

GitHub Copilot (cloud) latency
Public engineering talks from GitHub / Microsoft claim Copilot’s average response time under 200 ms for completions across millions of daily requests. 
YouTube
+1

Field benchmarks report inline suggestion latencies around ~130 ms median in practice. 
Skywork

Many users note that network conditions and service load affect response time, with occasional slower experiences reported. 
GitHub
+1

These figures include network round trip time plus server processing time and represent response time, not purely local model inference latency. Cloud response timing is inherently limited by transport and queuing overhead.

Local GPU LLM inference (consumer hardware)
Benchmarks and tooling (like NVIDIA GenAI-Perf and MLPerf Client) define time to first token (TTFT) as the key metric for inference latency on GPUs like consumer-RTX. 
NVIDIA Developer
+1

Public guides for local LLM inference note that high optimisation, model quantisation, and GPU backend improvements drive very low TTFT, especially for smaller models scaled for consumer cards. 
apxml.com

While explicit published benchmarks for an RTX 5060 Ti are uncommon, broader inference benchmarks show sub-100 ms TTFT is achievable on capable consumer GPUs with warmed models (optimised libraries, model cached in VRAM, no cold load). 
apxml.com

Comparison: cold vs hot start

Local inference cold start:

Loading model weights from disk to GPU memory can take hundreds of milliseconds to seconds, depending on model size and storage speed.

Disk I/O and context initialisation dominate before any generation begins.

Local inference hot start:

Once the model is resident in VRAM and the GPU context is warmed, the actual generation launch latency (TTFT) for small / quantised models on RTX-class cards is measured in tens of milliseconds.

Larger models or unoptimised runtimes can push this higher but still generally stay below typical cloud+network latencies.

Cloud service (Copilot):

Cold vs hot on the server side is not directly observable to the client; GitHub uses caching and autoscaling to keep hot paths ready. However network transport typically adds tens of milliseconds even in good conditions.

Reported server-side averages under 200 ms include all overheads. 
YouTube

Summary of likely behaviour

For warm (hot) local inference, a consumer GPU running an optimised LLM has a first token latency that can be lower than cloud Copilot round-trip latency.

For cold local models, loading and initialisation can be slower than Copilot’s typical response time.

Copilot’s claimed <200 ms response times are end-to-end (network + inference), not pure inference. 
YouTube

If you need precise numbers for a specific GPU (e.g. RTX 5060 Ti) and model configuration, those require direct benchmarking with tools such as MLPerf Client or NVIDIA GenAI-Perf rather than general claims. 
NVIDIA Developer

Ok does this feel better as a dev?

Yes. From a developer experience perspective, local inference generally feels better once the system is set up and kept warm.

The key reasons are predictability and immediacy. With a local model on a GPU, time to first token is consistent and not affected by network jitter, regional routing, or backend load. Once hot, responses start effectively instantly at human perception scales. That consistency matters more than raw averages when you are typing.

Cold start is the main downside. Restarting the editor, rebooting, or swapping models introduces noticeable pauses that Copilot largely hides through always-on infrastructure. Memory pressure, VRAM limits, and occasional driver issues also add operational friction.

Copilot still feels smoother out of the box. No setup, no tuning, no resource management, and strong model quality with large context windows. For many developers that convenience outweighs latency differences.

In practice, local inference feels better if you value tight feedback loops and control, and are willing to manage the system. Copilot feels better if you value zero maintenance and consistently strong suggestions, even with slightly higher latency.

Do higher end GPUs have better latency or not really?

Short answer: yes, but with diminishing returns, and only up to a point.

For time to first token, higher-end GPUs help mainly in two ways: faster single-batch compute and more memory bandwidth. That reduces the latency of the initial forward pass. Moving from an entry-level GPU to a mid-range one produces a noticeable improvement. Moving from mid-range to high-end produces a much smaller one.

Once the model fits comfortably in VRAM and is not memory-bandwidth bound, TTFT is already in the tens of milliseconds. At that point, higher-end GPUs do not change the subjective feel much. Human perception does not meaningfully distinguish 10 ms from 4 ms in this context.

Where high-end GPUs matter more is throughput and headroom. They handle larger models without quantisation, longer contexts, higher batch sizes, and concurrent requests. They also reduce tail latency under load. These factors affect sustained generation and multi-tasking more than first token latency.

Cold start is mostly unaffected by GPU tier. Loading weights from disk, initialising CUDA contexts, and setting up kernels dominate cold latency. Faster GPUs do not meaningfully reduce that, though faster storage and more VRAM can.

In practical terms:
Low to mid-range GPUs improve latency significantly over CPU or iGPU.
Mid-range to high-end GPUs bring marginal TTFT gains but large capacity and throughput gains.
If your model already fits and runs comfortably, upgrading the GPU rarely changes how fast the first token appears.

And if they gen at ~60 token/s how long is a typical compleation

At ~60 tokens per second, duration is easy to estimate and usually shorter than people expect.

A typical inline code completion is roughly 10 to 40 tokens. At 60 tokens per second, that takes about 170 to 670 milliseconds of generation time. With time to first token added, total wall time is commonly under one second.

Slightly larger completions, such as a full function body, are often 50 to 150 tokens. That corresponds to about 0.8 to 2.5 seconds of generation.

Longer responses, for example multi-function edits or explanations, can run 300 to 500 tokens and take 5 to 8 seconds, but these are less common in inline developer workflows.

In practice, perceived latency is dominated by time to first token. Once generation starts, streaming at 60 tokens per second feels effectively instantaneous for normal completions.

OK so copilot might still win then

Yes, that is a reasonable conclusion.

If you look at the full experience rather than just time to first token, Copilot can still feel faster overall. Its completions are often shorter, more aggressively truncated, and well-tuned to stop early. That means even with higher TTFT, total wall time can be comparable or better for common inline suggestions.

Copilot also benefits from very strong prompt engineering and model selection optimised specifically for IDE usage. It often produces a usable completion in fewer tokens, which directly reduces generation time.

Local models tend to generate more verbosely unless carefully tuned. If they emit 2 to 3 times as many tokens, even a higher token rate and lower TTFT may not fully offset that.

So the practical trade-off is:
Local inference usually wins on raw TTFT once hot.
Copilot often wins on brevity and relevance of completions.
Overall perceived speed can favour Copilot in many day-to-day coding scenarios, despite higher network latency.

That matches the intuition you are arriving at.

Oh maybe it's not worth getting a local GPU then.

That is a defensible position, and many developers reach it after running the numbers.

If your primary goal is inline code completion with low friction, Copilot already sits close to the perceptual limit of usefulness. The latency difference rarely blocks flow, and the quality to token ratio is very good. In that narrow use case, a local GPU is hard to justify on cost alone.

A local GPU starts to make sense when at least one of these is true. You want offline or air-gapped use. You want full control over models, prompts, and data locality. You frequently do longer generations, refactors, or multi-file edits where throughput and context matter more than brevity. You already need the GPU for other workloads, so marginal cost is low.

If none of those apply, Copilot remains the economically rational choice. A consumer GPU plus power, heat, and maintenance is a real ongoing cost for a modest experiential gain in this specific workflow.

A hybrid approach is also common. Copilot for inline completions, local models for heavier tasks where waiting a few seconds is acceptable and control matters.

So no, you are not missing something obvious. For many developers, a local GPU does not clearly win on developer experience alone.

I don't know what to go for, the big GPU or a bunch of cloud

You are facing a capacity versus convenience trade-off. Answer it by matching your actual use patterns against three clear decision axes: workload type, cost, and control/privacy.

Here’s a structured way to decide:

1. What type of inference work you actually do
If your tasks are mostly short, inline code completions and occasional prompt queries (a few tens of tokens), cloud services like Copilot are already near the best possible latency/quality trade-off. Local GPUs rarely outperform cloud for overall developer experience in that narrow case.

If you also plan to run larger jobs (batch completions, long code generations, retraining/finetuning, embeddings at scale), and especially if those jobs are frequent, then local GPU capacity starts to pay off because cloud costs multiply with usage.

2. Cost model
Local GPU:

One-time capital expense plus electricity and maintenance.

Costs are predictable once purchased.

Best if you already run other GPU workloads (ML, data science, simulations).

Cloud GPU:

Operational expense that scales with usage.

Zero maintenance or hardware depreciation risk.

Good for bursty or unpredictable demand.

Rough rule of thumb: If you expect continuous GPU usage for many hours per week over months, local hardware becomes cost-effective. If your usage is sporadic, cloud usually costs less.

3. Latency and development experience
Cloud services add unavoidable network latency (tens to hundreds of ms), but for many dev workflows this is masked and not disruptive. A local GPU avoids that network overhead, but as we discussed, the felt difference is small for short completions once warm.

For long generation tasks (100+ tokens), local throughput can exceed cloud latency by a bigger margin, but that only matters if you actually need those longer outputs.

4. Control and privacy
Do you need strict data locality or to avoid sending code to third parties? Local inference wins there. If this matters to your employer or project confidentiality, that’s a strong reason to invest in hardware.

Practical comparison scenarios

Scenario A: Primarily inline completions, occasional longer queries
Cloud first. Use Copilot or hosted LLM services. Local GPU adds complexity and marginal benefit.

Scenario B: Frequent long completions, batch tasks, embeddings, larger models
Local GPU becomes valuable. A higher-end GPU (e.g. RTX 4090/50 series with large VRAM) gives low latency and high throughput.

Scenario C: Unpredictable or bursty heavy workloads
Cloud GPU instances (e.g. Lambda, CoreWeave, RunPod) let you pay only for what you use without owning hardware.

Which GPU tier if local
You asked about big GPU versus cloud:

Big GPU (high VRAM, high throughput) is beneficial if you want to run larger models well and do heavy tasks locally. It reduces both cold and hot latency for bigger models and gives more headroom.

A mid-range GPU might suffice for smaller models but will struggle with very large contexts.

If you go local, aim for something with plenty of VRAM (24 GB+) if you want to run larger, higher-quality models without quantisation. Cheaper cards are fine only for lightweight models.

Cloud alternatives
You can mix:

Use cloud for occasional heavy tasks and keep local GPU for light to moderate work.

Use cloud inference APIs with good latency (e.g. services that place servers near you) to combine convenience and performance.

Summary decision aid
Write down:

How many hours per week you expect to do heavy inference?

What maximum token budget you need per query?

Whether data privacy is a requirement?

Your cost tolerance (capex versus opex)?

If heavy usage, privacy, predictable cost are priorities, local higher-end GPU is justified.
If low maintenance, unpredictable usage, convenience are priorities, cloud is better.

If you want, tell me your expected weekly usage and task types, and I can map that to rough cost estimates for both paths.

what kind of token per sec does copilot get

There is no precise public specification of how many tokens per second GitHub Copilot actually generates in terms of raw throughput (tokens/sec) on the cloud. GitHub does not publish a TPS number for Copilot’s service akin to what you see in GPU benchmark reports. What is available are latency statistics and throughput improvements reported by GitHub itself. 
Skywork
+1

From published and community sources the practical performance profile of Copilot looks like this:

GitHub states that its code completions typically arrive with sub-200 millisecond response times for inline suggestions in normal conditions, averaged over many requests. That figure includes network round trip, server processing, and streaming. 
InfoQ

GitHub’s recent performance updates claim higher token-per-second throughput and lower latency than before, with “3x higher token-per-second throughput” in their internal metrics for suggestion generation on updated custom models. 
The GitHub Blog

Independent testing and community reports (e.g. measured groomed completions under 500 ms) align with Copilot delivering usable suggestions in hundreds of milliseconds, though there is variability based on load, connection quality, and context size. 
Augment Code

Because the service streams tokens as they arrive and because the latency metrics are end-to-end (not purely generation speed), an explicit token-per-second rate would have to be inferred rather than directly published. The available statements about “higher TPS” are relative improvements rather than absolute figures. 
The GitHub Blog

What you can reasonably conclude based on what Copilot reports and external latency measurements

Copilot’s effective token generation is high enough that the IDE feels responsive (<200 ms for typical inline suggestions). 
InfoQ

GitHub’s internal optimisations claim multi-fold improvements in per-token throughput compared to earlier versions. 
The GitHub Blog

Actual tokens-per-second speed on the cloud is not officially documented and depends on the model used, load balancing, and engineering stacks behind Copilot’s service.

Context compared to local inference

Local GPUs often benchmark raw token throughput (e.g., hundreds of tokens per second up to thousands on high-end hardware). But cloud services do not expose that metric in the same way because they are focused on latency to results as perceived by the developer rather than on raw generation speed. Copilot’s tight end-to-end latency partly masks the raw tokens/sec because it optimises for suggestion turnaround rather than raw output speed.

Bottom line

Copilot does not publicly provide a clean “tokens per second” metric. What is documented is that its perceived latency for suggestions is often sub-500 ms, and GitHub actively reports improvements in generation throughput on the backend, which implies competitive tokens/sec performance for common coding tasks relative to end-to-end usage patterns. 
Skywork
+1

If you need exact numeric tokens/sec figures for the specific model version Copilot uses in your IDE, the only reliable method is empirical measurement (timing streamed responses and dividing by token count) because GitHub does not publish those figures publicly.

Ok but how many tokens is te max completion

GitHub does not publish a single fixed “maximum completion length” for Copilot, but in practice the limits are quite low, by design.

For inline code completions, Copilot typically caps output at tens of tokens, not hundreds. Empirically, most suggestions fall in the 10 to 40 token range. Longer inline suggestions are aggressively truncated to avoid blocking typing flow.

For explicit Copilot Chat requests such as “generate a function” or “explain this code”, the effective completion length is higher but still constrained. Typical responses are on the order of a few hundred tokens, commonly 200 to 500 tokens, depending on the request and context. It is not intended for very long, free-form generation in the way general-purpose chat models are.

There is no supported mode where Copilot will emit thousands of tokens in one go. This is an intentional product decision, not a hardware limitation. Shorter outputs reduce latency, cost, and distraction, and they align better with IDE workflows.

So in concrete terms:
Inline completions: usually capped around a few dozen tokens.
Chat-style responses: a few hundred tokens at most.
Very long generations: effectively out of scope for Copilot.

This is one of the main reasons Copilot can feel fast even if raw tokens-per-second is not exceptional. It simply does not try to generate much.

So how do they gerenate tokens <200ms

They achieve sub-200 ms perceived latency by not treating the problem like general text generation. Several techniques stack together.

First, they minimise how many tokens are generated. Inline Copilot suggestions are short, often 10 to 30 tokens. At that size, raw generation time is small even if tokens per second is only moderate.

Second, the model is almost certainly speculatively decoding. This means a lightweight draft model predicts several tokens ahead, and a larger model verifies them in parallel. When the draft is mostly correct, multiple tokens are emitted at once. This collapses what would normally be many sequential decoding steps into one or two GPU passes.

Third, they run on hot, pre-initialised infrastructure. Models are always resident in VRAM, CUDA contexts are warm, kernels are cached, and requests are aggressively batched across users. There is no cold start from the client’s point of view.

Fourth, they aggressively optimise prompts and context. Only a small slice of your file, plus heuristically chosen surrounding code, is sent. Shorter context reduces attention cost, which directly lowers time to first token.

Fifth, they front-load the pipeline. As you type, the IDE speculatively sends context before you pause. In many cases, generation has already started before you consciously request a completion. What feels like a single request is often overlapped with typing.

Finally, they tune for latency over raw quality. The models used for inline completion are specialised, smaller than frontier chat models, and heavily optimised. They trade generality for speed and predictability.

Put together:
Short outputs.
Speculative decoding.
Always-hot GPUs.
Small, curated context.
Pre-emptive requests.
Latency-optimised models.

That is how tokens appear “almost instantly” even though normal autoregressive decoding would suggest much higher latency.

Would it be hard to beat all this despite the network latency

Yes. It would be hard, and for the same reasons you have already uncovered.

Beating Copilot is not about raw GPU speed. It is about system-level optimisation. Network latency is only a small part of the budget, and they have already amortised or hidden much of it.

To consistently beat Copilot end to end, a local system would need all of the following at once. A latency-optimised model rather than a general LLM. Very aggressive output limits. Speculative decoding or equivalent techniques. Continuous warm state with no cold starts. Tight IDE integration that pre-emptively triggers inference while the user is still typing. Careful prompt curation to minimise context length. Tuned stopping criteria to end generations early.

Most local setups have none or only some of these. They often run larger, more general models, with longer contexts, no speculative decoding, and reactive rather than predictive invocation. Even with zero network latency, they frequently lose on perceived speed because they generate more and do more work per request.

The network adds maybe 30 to 80 ms in good conditions. Copilot has already compressed the rest of the pipeline to fit inside a few hundred milliseconds. Removing the network does not buy you enough budget to offset missing the other optimisations.

So yes, it is entirely reasonable to conclude that beating Copilot “despite the network” is hard unless you are willing to build a Copilot-like system yourself. For an individual developer, that effort usually outweighs the benefit.

They keep the connection open?

Yes. Effectively, yes.

Copilot maintains a long-lived, persistent connection between the IDE and the backend rather than opening a fresh connection for every completion. This is typically done over HTTPS with connection reuse or a WebSocket-like streaming channel, depending on the IDE and platform.

That matters because it removes repeated TCP and TLS handshakes, which alone can cost tens of milliseconds. With a warm connection, the request can be sent immediately and responses can start streaming as soon as the server emits tokens.

On top of that, the client often sends speculative or incremental context updates as you type. The backend may already be preparing or partially executing a request before you explicitly pause and accept a suggestion. From your point of view, it looks like a single fast response, but internally work is overlapped with typing.

So while there is still unavoidable network latency, it is reduced to the minimum practical level. The connection is hot, the server is hot, and the request is often half-done before you realise you asked for it.

This is another reason why local setups do not automatically feel faster even though they remove the network hop.
