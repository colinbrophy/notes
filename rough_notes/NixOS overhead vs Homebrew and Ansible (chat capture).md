---
tags: [draft, ai-written]
---

## Context / goal

Capture a chat exploring why NixOS can feel “high overhead” for desktop experimentation (vs Homebrew / imperative installs), and why declarative approaches (Terraform/Ansible/Nix) fit servers better than full-machine imaging.

## Key points

- NixOS overhead largely comes from strict declarativity, rebuild-driven changes, and store purity/isolation that clashes with tools expecting mutable/FHS-like environments.
- “Simple install” often becomes “edit config + rebuild”, or packaging/overrides when nixpkgs lags or the tool doesn’t fit the model.
- Self-updating tools (e.g. `yt-dlp`) optimize for fast upstream change; NixOS resists self-mutation, creating constant friction for fast-moving software.
- Servers benefit from recorded intent and controlled change; images capture state but not intent, while declarative tools preserve “why” and reduce drift.
- Ansible feels lower-friction than NixOS because it’s a higher-level, tolerant layer over an imperative substrate (you can codify selectively after the fact).
- Desktops optimize for fast, reversible local mutations and flow; rebuild/reboot/update ceremony is ergonomically costly.

## Cleanup targets

- [[NixOS]]
- [[Homebrew]]
- [[Ansible]]
- [[Declarative configuration]]
- [[Reproducibility]]
- [[yt-dlp]]

## Chat (verbatim)

What is it about NixOS's design that makes the overhead he talks about here.

The “overhead” he is describing follows directly from several core NixOS design decisions, rather than from bugs or poor tooling.

First, NixOS is strictly declarative and rebuild driven. Any change to system state is meant to go through evaluation of Nix expressions and a full rebuild of the relevant derivations. That means even trivial experimentation often requires editing configuration, running a rebuild, and dealing with evaluation or build failures. This adds fixed cognitive and time cost compared to imperative systems where a tool can be installed, updated, or removed immediately. This is the friction he repeatedly runs into when he just wants to try a new editor, CLI, or runtime quickly 

pasted

.

Second, NixOS enforces isolation and purity through the Nix store. Binaries do not assume FHS paths, mutable system libraries, or ambient dependencies. Many developer tools, especially fast moving ones like editors, language runtimes, and cloud CLIs, implicitly assume a mutable system with conventional paths and ad hoc installs. On NixOS, those assumptions break, so users must patch them via wrappers, extra configuration, or custom flakes. The overhead here is not runtime performance but adaptation work every time a tool does not already fit the Nix model.

Third, update semantics are centralized and conservative. Applications are updated via channels or flakes, not by self updating. When upstream software expects to manage its own updates, the NixOS model creates friction: users must wait for packaging updates, track unstable channels, or override versions manually. This explains his frustration with tools like JetBrains IDEs or rapidly evolving editors, where clicking “update” elsewhere just works but on NixOS triggers breakage or manual intervention 

pasted

.

Fourth, reproducibility raises the cost of experimentation. The same mechanisms that guarantee rollbacks and clean state also mean that every experiment becomes part of a global, reproducible configuration. For someone who frequently tries new tools and discards them, the effort of modeling each experiment declaratively outweighs the benefits. This is why he describes enjoying tinkering when it is optional, but resenting it when it becomes mandatory just to get work done 

pasted

.

In short, the overhead comes from NixOS optimizing for long term reproducibility, purity, and explicit state at the expense of low friction, ad hoc experimentation. For users with stable toolchains, this tradeoff pays off. For users who constantly trial new tools and expect imperative, self updating workflows, the design itself creates persistent friction rather than removing it.

Sources
So stuff that is just a simple brew install becomes what?

In NixOS, something that would be a simple brew install turns into one of several heavier weight workflows, depending on how well the tool fits the Nix model.

If the tool is already packaged in nixpkgs, it becomes a configuration change. You add the package to a system or user package list, rebuild, and wait for evaluation and activation. Even for a trivial CLI, this is edit, rebuild, test, rather than a one line imperative action.

If the tool is not packaged, it becomes packaging work. You either write a Nix expression or flake that fetches the upstream binary or source, declares its dependencies explicitly, and adapts paths and runtime assumptions. For tools that assume FHS layouts, mutable directories, or self updating, this can escalate quickly from minutes to hours.

If the tool expects to manage its own updates, it becomes a version pinning and override problem. You track unstable channels, override versions, or vendor the package yourself. What would be an automatic background update elsewhere becomes ongoing maintenance work.

If you want it temporarily, it still has ceremony. You can use nix shell or nix run, but that requires knowing the right attribute, dealing with flakes, and understanding how the environment is composed. It is not equivalent, mentally or operationally, to installing and forgetting.

So the mapping is roughly this: brew install foo becomes either “edit config and rebuild,” “write or maintain a package,” or “enter a disposable shell and hope it behaves.” The overhead is not complexity per step, but the fact that every step is explicit, reproducible, and therefore unavoidable.

Almost all CLI tools have brew support too. It supports Mac, Linux and WSL with no work from devs side. So it tends to be everywhere, especially as it's the main way on Mac.

Yes, and that observation highlights the core mismatch very clearly.

Homebrew works because it is an imperative, FHS aligned, lowest common denominator layer. A developer can ship a single tarball or script that assumes standard paths, dynamic linking, and a mutable filesystem. Homebrew then standardises the install location and wraps just enough to make it work on macOS, Linux, and WSL. From the tool author’s perspective, supporting Homebrew is effectively zero extra work, so it becomes the default distribution path for CLIs.

NixOS deliberately rejects that model. It does not provide a stable global filesystem layout, does not allow tools to assume ambient libraries, and does not tolerate self mutation. As a result, the “it just works everywhere” property of Homebrew CLIs collapses. Each tool must either already be adapted to NixOS, or the user must do that adaptation locally.

This is why the cost difference feels so stark. On macOS or Ubuntu, Homebrew is a thin convenience layer over normal Unix expectations. On NixOS, Homebrew style tools clash with the system’s fundamental guarantees. The friction is not accidental or fixable by better UX; it is the price of enforcing purity and reproducibility in an ecosystem that overwhelmingly optimises for imperativeness.

That also explains why this disproportionately affects people who explore new CLIs frequently. The wider CLI ecosystem has converged on Homebrew as the de facto cross platform delivery mechanism. NixOS sits outside that convergence by design, so every “brew install” implicitly becomes a translation exercise into a different model of software distribution.

Ans some tools just want to self update for good reason.

Correct. From the tool’s perspective, self updating is often the rational design choice.

Many modern CLI tools ship fast, frequent releases, track external APIs, or bundle models, plugins, or language runtimes that change independently of the host system. Self updating lets the tool deliver fixes immediately, avoid distro lag, and reduce support burden. It also lets developers treat the CLI as an application, not a system component.

This again conflicts directly with NixOS’s guarantees. NixOS assumes that software is immutable once built and that all changes flow through the package manager. A self updating binary violates referential transparency, breaks reproducibility, and can invalidate rollbacks. So NixOS must either disable self updates, patch around them, or force users to opt into wrappers and overrides.

The result is predictable friction. A tool that responsibly self updates elsewhere becomes “broken” or “hostile” on NixOS, even though it is behaving sensibly for its problem domain. Users then carry the cost: pinning versions, chasing unstable channels, or debugging why an update mechanism fails inside an immutable store.

This is the underlying reason his experience degrades over time. The ecosystem he is operating in expects tools to evolve continuously and autonomously. NixOS expects tools to be static artefacts managed centrally. Neither side is wrong, but the impedance mismatch turns normal developer workflows into ongoing maintenance work.

yt-dlp is a good one, needs fast updates

yt-dlp is an excellent example because it makes the tradeoff unavoidable.

yt-dlp operates in an adversarial environment. Websites change frequently, often deliberately, and break download logic. A working build today can be unusable tomorrow. Fast updates are not a convenience; they are part of the tool’s correctness model.

On most systems, yt-dlp solves this by self updating or by encouraging installation methods that update daily with minimal friction, such as brew upgrade, pip install -U, or a bundled updater. The expectation is that users stay near head and that breakage is resolved upstream, not by the distro.

On NixOS, that model does not fit. If you install yt-dlp declaratively, you are pinned to whatever version is in your channel or flake. When YouTube changes something, the tool breaks, and the fix exists upstream but not yet in nixpkgs. At that point, the user must switch channels, override the package, fetch a newer source, or abandon the declarative install entirely. All of that is overhead introduced purely by the update latency.

This illustrates the deeper issue. NixOS assumes that the package manager controls update cadence. yt-dlp assumes that reality controls update cadence. For tools tied to fast moving external systems, centralised, reproducible updates are the wrong abstraction. The cost shows up as friction, not instability, but it is constant and cumulative.

So when he says a “simple install” turns into work, yt-dlp is the cleanest case. On other systems, updating is part of using the tool. On NixOS, updating becomes a packaging problem, and that is exactly the kind of overhead he is reacting to.

yt-dlp suggests you download and let it self update even over bew.

Yes, and that recommendation is very deliberate on their part.

yt-dlp explicitly treats itself as a self updating application, not a distro managed utility. Even when installed via Homebrew, the project’s own documentation still points users toward its internal updater or direct binary download. Homebrew is effectively just a bootstrap mechanism.

The reason is control over update latency. yt-dlp cannot afford to wait for downstream packaging cycles when upstream sites change daily or weekly. A broken extractor is not a minor bug; it is total loss of functionality. By owning the update path, the project can push fixes immediately and keep support manageable.

This is exactly where NixOS becomes a poor fit. From NixOS’s perspective, a binary that mutates itself is violating core assumptions. From yt-dlp’s perspective, not mutating itself is irresponsible. The tool is behaving correctly for its domain, but that correctness depends on bypassing the system package manager.

That is why yt-dlp ends up being such a sharp example in these discussions. It exposes the fundamental boundary:

On most systems, including macOS, Linux, and WSL, Homebrew is permissive enough that a self updating tool can coexist with it. On NixOS, coexistence is not allowed without opting out of the model. The user must either abandon declarative management for that tool or accept breakage until the package catches up.

So when someone says “this should just be a simple install”, yt-dlp shows why that expectation is reasonable in today’s CLI ecosystem, and why NixOS’s design makes that expectation expensive to satisfy.

Even homebrew is too slow.

Exactly, and that point matters.

For a class of tools like yt-dlp, even Homebrew’s update cadence is already too slow. That is why the project recommends bypassing package managers entirely and using a self updating binary. When upstream breakage can happen overnight, “daily” or even “same day” distro updates are insufficient.

This puts NixOS at the extreme end of the mismatch. Homebrew is already laggy relative to the problem domain, but it is still acceptable because it does not prevent escape hatches. You can install once and then let the tool mutate itself. NixOS removes that escape hatch by design.

So the layering looks like this:

Upstream reality changes faster than Homebrew.
Homebrew changes faster than most Linux distros.
NixOS deliberately changes slowest because reproducibility and review are the priority.

For tools whose correctness depends on tracking upstream reality closely, NixOS’s strengths become liabilities. The system insists on centralised, audited updates in a context where decentralised, immediate updates are the only viable strategy.

That is why “even Homebrew is too slow” is not a complaint about Homebrew. It is evidence that some software categories fundamentally do not align with distro managed update models at all. NixOS simply makes that incompatibility impossible to ignore.

why is it then that for servers, imaging and backing them up is less popular than terraform, ansible or the NIX approach?

Because servers and developer machines optimise for opposite failure modes.

Server environments prioritise long lived correctness, controlled change, and auditability. Imaging and restoring whole machines works, but it scales poorly once you have many hosts, frequent changes, and partial divergence. Tools like Terraform, Ansible, and NixOS exist because servers benefit from declarative intent rather than opaque snapshots.

An image captures state, not meaning. It tells you what the server looked like, not why it looks that way. As soon as you need to change one thing, roll out a security fix, or debug drift, images become liabilities. You either rebuild and redeploy entire images or accumulate undocumented mutations. At scale, that becomes brittle and expensive.

Declarative systems invert that. You describe desired state, and the system converges toward it. Changes are reviewable, composable, and incremental. Rollouts can be staged. Failures are localised. This maps well onto servers, where change is deliberate, infrequent relative to runtime, and centrally coordinated.

Developer machines are the opposite. They optimise for rapid, ad hoc experimentation, tool churn, and local autonomy. The “why” behind each installed tool is often unimportant. The cost of drift is low, and breakage is acceptable if it unblocks work quickly. In that context, imaging or imperative installs are fine, and strict declarative control becomes friction.

So the distinction is not ideological. It is economic. Servers pay the cost of declarative overhead once and amortise it over long lifetimes and many machines. Developer machines pay that cost repeatedly for short lived experiments. That is why Terraform, Ansible, and Nix style systems dominate server infrastructure, while snapshotting and imperative tooling remain common on personal machines, even though the underlying technology could be shared.

accumulate undocumented mutations.

So the core issue is lack or recording of intent? This is a maintence pain?

Yes. That phrase is getting at exactly that.

The core problem is not mutation itself, but unrecorded intent. When changes happen without being captured as intent, they become indistinguishable from accidents. Over time, the system accumulates state that no one can confidently explain, reproduce, or safely modify. That is the maintenance pain.

On servers, undocumented mutations are dangerous. You cannot tell which changes are required for correctness, which are historical leftovers, and which are accidental. This makes upgrades risky, debugging slow, and recovery uncertain. Imaging preserves the result of those mutations, but it does not restore understanding. You can bring the system back, but you do not regain the knowledge of why it works.

Declarative systems exist to solve that exact problem. They force intent to be written down. Every package, service, version, and dependency is there because someone declared it. That makes review, rollback, and reasoning possible months or years later, often by someone else.

On developer machines, the same lack of recorded intent is usually tolerable. If something breaks, the blast radius is small. The user often remembers what they were doing, or they can just reinstall. The cost of writing down intent for every experiment is higher than the cost of occasional breakage.

So yes, the issue is fundamentally about intent capture. Maintenance pain appears when systems live long enough, change often enough, and are touched by enough people that memory and tribal knowledge fail. Declarative tooling shifts work forward in time to prevent that failure. The tension you are circling is simply that not all systems benefit equally from paying that cost upfront.

The cost of writing down intent for every experiment is higher than the cost of occasional breakage.

The cost is acualtly quite low with ansible vs Nix OS

Yes, and that distinction is important. The cost difference is real, and it comes from where intent is captured and how strictly it is enforced.

With tools like Ansible, intent is recorded, but enforcement is loose and incremental. You can mutate the system freely, then later choose to codify what mattered. Playbooks tolerate existing state, partial drift, and imperative escape hatches. That makes the marginal cost of recording intent low. You only formalise what proves valuable.

NixOS captures intent at a much lower level and enforces it globally. The system strongly prefers that all meaningful state be declared upfront. Experiments are not just recorded after the fact; they must be modelled before they exist. That shifts the cost from “later, if needed” to “now, always”.

So the tradeoff is not declarative versus imperative in the abstract. It is strictness of intent capture.

Ansible lets you say “this is what I care about, ignore the rest”.
NixOS says “everything you care about must be declared, or it does not exist”.

On servers, that strictness pays off because almost everything does matter, eventually. On developer machines, especially during experimentation, most changes are provisional. For those, Ansible’s low friction, opt in intent recording matches the economics better, while NixOS’s all or nothing model makes the same intent recording feel disproportionately expensive.

That is why Ansible often feels like a sweet spot for maintenance without friction, and NixOS feels like over capture unless the system itself is the product.

Ansible is a thin layer on top of the imperitive model and is more high level than NIX so is less painful.

Yes. That is a precise way to put it, and it explains the difference cleanly.

Ansible is a thin, high level layer over an imperative substrate. The underlying system is still mutable, stateful, and forgiving. Ansible describes desired effects, but it executes them imperatively and tolerates pre existing state. If something is missing, it installs it. If something extra exists, it usually ignores it. That keeps friction low because the system’s native behaviour is unchanged.

NixOS is not a layer. It replaces the substrate. The imperative model is not underneath; it is actively constrained. State outside the declaration is either ephemeral or treated as suspect. That forces a much lower level of description and tighter coupling between intent and reality.

Because Ansible sits above the system, it can afford to be opinionated only where it matters. Everything else can remain messy, ad hoc, and undocumented without breaking the model. This makes experimentation cheap and retroactive formalisation possible.

Because NixOS is the system, experimentation must pass through the model. The pain is not that Nix is more complex, but that it is more complete. Completeness increases the surface area of intent that must be expressed.

So your framing is right. Ansible feels less painful not because it is weaker, but because it is strategically incomplete. NixOS feels painful in exploratory workflows because it is intentionally total.

In truth you want to be able to do quick mutations on a desktop. Nobody want to reboot for an update.

That is the practical conclusion most people eventually reach.

On a desktop, you want fast, reversible, low ceremony mutations. You install something, try it, update it, maybe delete it an hour later. The feedback loop matters more than global correctness. Reboots, rebuilds, and evaluation steps break that loop. Even if they are technically safe, they are ergonomically wrong for interactive work.

This is where the NixOS model clashes hardest with desktop expectations. System rebuilds, activation steps, and occasional reboots are acceptable on servers because change is scheduled and infrequent. On a desktop, change is continuous. Forcing updates through a rebuild pipeline turns every small action into an interruption.

Imperative systems tolerate this because they embrace local inconsistency. A package can update itself while you are working. A tool can patch itself in place. Nothing insists on global coherence. If something breaks, you fix it or move on. That tradeoff is acceptable on a personal machine.

So yes, people do not want to reboot for an editor update, a CLI fix, or a broken extractor. They want mutation to be cheap. Declarative systems deliberately make mutation expensive to protect long term state. That protection is valuable in some contexts, but on a desktop it often optimises for the wrong problem.

The thread you have been pulling on is consistent throughout: NixOS is excellent at preserving intent and preventing decay, but desktops optimise for flow, not preservation. When those goals collide, flow usually wins.
