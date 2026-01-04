---
tags: [draft, ai-written]
---

## Context / goal

Capture a discussion about switching from Linux to OpenBSD (especially on laptops), what is gained/lost in system coherence and security model, and how Linux’s ecosystem pull interacts with compatibility layers (Wine/Proton) and virtualisation (GPU passthrough, dual boot).

## Key points

- Linux offers far broader software/hardware support, performance tooling, and container ecosystems; OpenBSD trades breadth for coherence, simplicity, and legibility.
- On laptops, OpenBSD is typically weaker on power management, graphics stack polish, and Wi‑Fi, even with careful hardware choice.
- OpenBSD security posture emphasises small, coherent base + developer-facing mitigations (privilege separation, `pledge`, `unveil`) rather than admin-managed MAC policy like SELinux.
- “Understandability” differences show up mainly during debugging: OpenBSD tends to have fewer layers and more direct `/etc` → behaviour mapping.
- Linux’s dominance is reinforced by ecosystem feedback loops; BSD persists mainly in niches (network/security appliances, embedded, selected infra).
- Proton/Wine make Linux a more universal substrate by hosting compatibility layers; for non-gaming Windows apps, VMs (especially with GPU passthrough) are often the most reliable path.

## Cleanup targets

- [[OpenBSD]]
- [[Linux]]
- [[power management]]
- [[SELinux]]
- [[pledge]]
- [[unveil]]
- [[Wine]]
- [[Proton]]
- [[GPU passthrough]]
- [[dual boot]]

## Chat (verbatim)

If it switched from openbsd from Linux what would I miss? I can choose the hardware

If you switched from Linux to OpenBSD, with full control over hardware choice, what you would miss falls into several clear categories. This assumes a technically competent user who is comfortable configuring systems manually.

First, software availability and ecosystem depth. Linux has vastly broader third-party software support. Many applications are developed for Linux first, sometimes exclusively. Examples include modern desktop environments at full feature parity, newer developer tools, container tooling, vendor SDKs, proprietary software, and some language runtimes that lag or are absent on OpenBSD. While OpenBSD ports are high quality, the catalogue is much smaller and more conservative. You would miss rapid access to new upstream releases.

Second, hardware support breadth. Even if you can choose hardware, Linux supports a far wider range of devices and features. Linux tends to get support for new CPUs, GPUs, Wi-Fi chipsets, and peripherals much earlier. On OpenBSD you would miss high-performance GPU drivers, modern power management on laptops, advanced Wi-Fi features, and vendor-specific firmware integrations. Choosing supported hardware mitigates this, but does not eliminate the gap.

Third, performance tuning and scalability options. Linux offers far more tunables, schedulers, filesystems, and performance tooling. You would miss cgroups, namespaces, io_uring, eBPF, advanced NUMA controls, and the ability to heavily optimise for specific workloads. OpenBSD prioritises correctness, simplicity, and predictability over raw performance and configurability.

Fourth, containerisation and orchestration. Linux is the foundation of containers. You would miss Docker, Kubernetes, podman, systemd-nspawn, and the entire container ecosystem as it exists today. OpenBSD has jails-like isolation mechanisms such as pledge and unveil, but these solve different problems and are not a replacement for container workflows.

Fifth, filesystems and storage features. Linux offers many mature filesystems and storage stacks, including ext4, XFS, Btrfs, ZFS with Linux-specific tooling, advanced RAID and volume management, and broad encryption options. OpenBSD primarily uses FFS and has more limited storage flexibility. You would miss snapshotting, advanced copy-on-write behaviour, and large-scale storage tooling.

Sixth, desktop experience, if relevant. Linux desktop support is significantly more polished. You would miss seamless Wayland support, modern compositors, better HiDPI handling, GPU acceleration, and broader application compatibility. OpenBSD desktops work, but feel spartan and conservative.

Seventh, community scale and documentation variety. Linux has an enormous global ecosystem. You would miss the sheer volume of tutorials, Stack Overflow answers, vendor documentation, and community tooling. OpenBSD documentation is excellent, but narrower in scope and assumes closer adherence to project philosophy.

What you would not miss, and what you gain, is also relevant context. OpenBSD gives you a much simpler, more coherent base system, extremely strong defaults, first-class documentation via man pages, integrated security design, and long-term stability. If your workloads are servers, networking, firewalls, or security-sensitive services, the trade-off can be favourable.

In short, you would miss breadth, speed of innovation, and ecosystem scale. You would gain consistency, auditability, and predictability. Whether that matters depends entirely on what you run and how much you rely on Linux-specific infrastructure.

So would running it on a laptop suck.

Short answer: for most people, yes.

On a laptop, OpenBSD is usable but meaningfully worse than Linux in several practical areas, even if you choose hardware carefully.

The main issue is power management. OpenBSD’s CPU frequency scaling and sleep states are basic compared to Linux. You will get noticeably worse battery life, less aggressive idle power saving, and fewer vendor-specific optimisations. Suspend and resume usually works on supported hardware, but it is slower and less reliable than on a well-supported Linux laptop.

Graphics support is another major limitation. OpenBSD relies on open, generic drivers. There is no modern GPU acceleration stack comparable to Linux. You miss proper Wayland support, modern compositors, and efficient video decoding. High-resolution and HiDPI displays work, but feel less polished and consume more power.

Wi-Fi is also weaker. OpenBSD supports fewer chipsets and often lacks newer standards and performance features. Throughput is lower, roaming is poorer, and power saving on wireless is less effective. You must choose a known-good Intel chipset to avoid frustration.

The desktop experience is functional but spartan. You can run X11 with a lightweight window manager, a browser, and editors, but it feels like a workstation from an earlier era. Modern desktop conveniences that are routine on Linux often require workarounds or are simply unavailable.

What does work well is stability and predictability. If you treat the laptop as a portable terminal, coding machine, or network diagnostics platform, OpenBSD can be quite pleasant. The system is quiet, consistent, and well-documented. Crashes and strange regressions are rare.

In practical terms, if your expectations are set by a modern Linux laptop with good battery life, smooth graphics, and broad hardware support, OpenBSD will feel like a regression. If your expectations are a robust, minimal, Unix-like environment and you are willing to trade comfort for simplicity and security, it is tolerable.

If you want, I can give a concrete hardware profile where OpenBSD laptops are least painful, or contrast it directly with Fedora on the same class of hardware.

But will the system layer feel more understadnble. /Etc isn't chaos.

Spelling and punctuation issues detected:

“understadnble” → “understandable”

“/Etc” → “/etc”

Corrected question:
“But will the system layer feel more understandable? /etc isn’t chaos.”

Answer:

Yes. This is one of the strongest arguments in favour of OpenBSD.

The system layer is substantially more understandable than on a modern Linux distribution. OpenBSD is designed as a single, coherent operating system rather than a kernel with a large, loosely coupled userland. That design goal shows everywhere.

Configuration is centralised, explicit, and conservative. Most system behaviour is controlled by small, plain-text files in /etc with clear man pages that describe not only syntax but intent. There is very little indirection. If a service is running, you can usually find its configuration in one obvious place, and the defaults are readable rather than auto-generated.

There is no equivalent of systemd sprawl, background generators, opaque state directories, or layers of abstractions that rewrite configuration at boot. Startup is controlled by simple rc scripts. Services do what their configuration says, and little else. If you disable something, it stays disabled.

The base system is also much smaller. Kernel, libc, toolchain, core utilities, and daemons are developed together. This means fewer surprises, fewer implicit dependencies, and far less “why is this component here” confusion. You can realistically read large parts of the system documentation end to end and form a mental model that holds.

In contrast, Linux distributions accumulate complexity from many sources: kernel features, distribution tooling, vendor patches, service managers, packaging scripts, and desktop integrations. None of this is inherently bad, but it does make the system layer harder to reason about as a whole. /etc often feels chaotic because it reflects that layered history.

The trade-off is flexibility and ecosystem integration. OpenBSD’s clarity comes from saying “no” a lot. You get fewer knobs, fewer background mechanisms, and fewer ways for software to be clever behind your back.

So yes: if your frustration is specifically that Linux no longer feels legible or audit-friendly at the system level, OpenBSD will feel calmer, tighter, and more understandable. Whether that is worth the laptop compromises is a separate question.

But mostly you don't have to touch this anyway, even as a technical power user

Correct.

On a modern Linux system, even as a technical power user, you rarely need to touch the deep system layer. For most workflows, the distribution insulates you from it effectively enough.

The difference is not frequency of interaction but quality of understanding when you do have to interact with it.

On Linux, the system layer often behaves as an implementation detail you work around rather than reason about. When something goes wrong, you are pushed into tooling and abstractions that are distribution-specific, stateful, and sometimes opaque. You can usually fix the problem, but the fix is often procedural rather than conceptual.

On OpenBSD, you touch the system less often as well, but when you do, the surface area is smaller and more legible. The configuration you edit is usually the configuration that is actually used. The logs you read are closer to the source of truth. The behaviour you observe tends to follow directly from documented mechanisms rather than emergent interactions between layers.

So the practical distinction is this:

On Linux, you mostly do not need to understand the system layer, until you suddenly do, and then it can be difficult to form a complete mental model quickly.

On OpenBSD, you also mostly do not need to touch it, but the system is structured so that understanding it is feasible when required.

If your current Linux setup is stable and you rarely debug system-level issues, OpenBSD will not materially improve your day-to-day experience. If you value the ability to reason about the entire system when something breaks, OpenBSD provides a noticeably better experience, at the cost of convenience elsewhere.

Give an example

A concrete example is network configuration.

On Linux, even for something as simple as “bring up Wi-Fi at boot”, what actually happens depends on several layers that may or may not be present: kernel drivers, udev rules, NetworkManager or systemd-networkd, wpa_supplicant, distribution defaults, and sometimes vendor glue. The configuration you touch is often not the configuration that ultimately decides behaviour. Debugging usually means chasing state across tools and logs.

On OpenBSD, the entire path is explicit. You create /etc/hostname.iwm0 (or the relevant interface). You put the SSID and key in that file. The rc system brings the interface up at boot. Logs go to a single place. If it does not work, there are only a few moving parts to inspect, and the man pages describe the full flow end to end.

Another example is starting a service.

On Linux, enabling a daemon often involves a unit file, drop-in overrides, dependencies pulled in by targets, generated units, and socket or path activation. A service may start even when you think it is disabled, because something else depends on it. Understanding why requires knowledge of systemd’s dependency graph and current state.

On OpenBSD, enabling a service usually means adding it to rc.conf.local. If it is not listed, it does not start. There are no implicit dependency activations. Startup order is predictable and documented. When a daemon is running, it is almost always because you explicitly asked for it.

A final example is privilege reduction.

On Linux, applications rely on discretionary mechanisms such as setuid helpers, capabilities, seccomp profiles, AppArmor or SELinux policies, often managed by packaging scripts and runtime tooling. These mechanisms are powerful but fragmented and hard to reason about globally.

On OpenBSD, pledge and unveil are built into the base system and used consistently. When a program is constrained, the constraints are usually visible, documented, and enforced by the kernel in a uniform way. You can often understand the security posture of a program by reading its source or man page alone.

These examples illustrate the same theme: Linux solves problems through layered, optional systems. OpenBSD solves them by making the base system smaller and more explicit. The result is not that you do more work, but that when you must intervene, there is less ambiguity about where control actually lives.

Does openbsd have a system like selinux?

No. OpenBSD does not have an SELinux-style mandatory access control framework.

There is nothing in OpenBSD that corresponds to the Linux Security Module stack, SELinux, AppArmor, or SMACK. You do not write global policy files that label objects and mediate access system-wide.

Instead, OpenBSD takes a different approach, based on three main mechanisms that are simpler and more local in scope.

First, traditional Unix permissions and file ownership remain the primary access control model. OpenBSD relies heavily on getting these defaults correct and keeping the base system small enough that they remain tractable.

Second, privilege separation and privilege dropping are used extensively in base daemons. Services are split into small processes with minimal permissions, often chrooted, and communicating over well-defined interfaces. This is done by the developers of the base system, not by administrators writing policy after the fact.

Third, OpenBSD provides pledge and unveil. Pledge allows a process to declare, at runtime, which classes of system calls it will need. Unveil allows a process to restrict its own view of the filesystem. These are opt-in, per-program, and usually enabled by the application itself rather than centrally enforced.

The important distinction is where complexity lives.

SELinux moves complexity into administrator-managed global policy. OpenBSD moves complexity into application design and base system defaults. You trade expressive, centrally enforced policy for simpler, composable constraints that are easier to reason about but less powerful.

So if you rely on SELinux for enforcing organisation-wide security policy or for confining unmodified third-party software, OpenBSD does not offer an equivalent. If your goal is to reduce the attack surface of the base system and make individual programs harder to exploit, OpenBSD’s model is effective and significantly easier to understand.

But pledge is doing that at the dev layer

Yes. That observation is correct, and it is an intentional design choice.

Pledge operates primarily at the developer layer, not the administrator layer. The application author decides what promises the process will make, and the kernel enforces those promises. The administrator does not normally write or manage pledge policy.

This is a fundamental difference from SELinux.

In SELinux, the security model assumes that applications are largely untrusted or unchanged, and that the administrator enforces confinement externally via global policy. The system can restrict a program even if the developer did nothing to support that restriction.

In OpenBSD, the model assumes that security should be built into the software itself. Developers explicitly declare what the program should be allowed to do, and the kernel ensures it cannot exceed that declaration. If a program does not use pledge, the administrator cannot retroactively apply an equivalent constraint.

There are consequences to this approach.

The upside is that pledge is extremely easy to reason about. The restriction is local, explicit, and tied directly to program logic. There is no policy language, no global rule set, no label explosion, and no ambiguity about why something is denied. When pledge fails, the program is killed and the reason is clear.

The downside is that you cannot use pledge as a universal confinement mechanism. It does not help with legacy binaries, closed-source software, or enforcing organisation-wide security policy. You are trusting developers to do the right thing, and trusting the base system to set strong defaults.

OpenBSD compensates for this by combining pledge with other measures: aggressive privilege separation in base daemons, minimal installed services, conservative defaults, and a small, auditable system. Security is achieved by reducing what exists and what runs, rather than by constraining everything after the fact.

So your intuition is right: pledge is not “SELinux but simpler”. It is a different philosophy entirely. It shifts responsibility left, into design and implementation, rather than right, into system administration and policy management.

The nature of Linux is it was fgluing together a bunch of projects.

So you end up with much more features but more complex

Yes. That is an accurate characterisation.

Linux is not a single operating system in the traditional sense. It is a kernel around which many independently designed projects are assembled. Each component is usually well-engineered in isolation, but they were not designed together, and they evolve at different speeds with different goals.

The result is feature accumulation through composition. New capabilities are added by introducing new subsystems rather than by simplifying existing ones. Over time, layers accrete: init systems, service managers, device management, networking stacks, security frameworks, desktop infrastructure. Each layer solves a real problem, but each also adds state, policy, and interactions that are difficult to reason about globally.

This is why Linux excels at breadth. It supports more hardware, more workloads, more deployment models, and more user expectations than any other Unix-like system. It is also why it becomes complex. Coherence is not enforced centrally, so complexity is managed through abstraction rather than eliminated.

OpenBSD takes the opposite approach. It enforces coherence by limiting scope. The base system is developed as a unit. Features are rejected if they add too much complexity relative to their benefit. Integration matters more than capability. The system remains understandable precisely because it refuses to become a platform for everything.

Neither approach is inherently superior. Linux’s “glue” model is what makes it dominant in servers, cloud, embedded, and desktop environments. OpenBSD’s integrated model is what makes it attractive to people who value legibility, auditability, and predictable behaviour.

Your framing captures the trade-off cleanly: Linux maximises features by composition, and complexity follows. OpenBSD minimises complexity by design, and feature breadth is the cost.

Why isn't BSd used more in security critical

It is mostly non-technical reasons, with some practical ones layered on top.

First, ecosystem gravity. Security-critical systems do not exist in isolation. They integrate with hardware vendors, cloud platforms, compliance tooling, monitoring, automation, and third-party software. Linux dominates those ecosystems. Using BSD often means swimming upstream on tooling, vendor support, and operational knowledge, even if the base system is sound.

Second, institutional risk aversion. Organisations value predictability of supply, staffing, and support more than conceptual elegance. Linux has large corporate backers, long-term support offerings, certifications, and a deep hiring pool. BSD projects are small, volunteer-driven, and intentionally conservative. That makes them trustworthy technically, but risky organisationally.

Third, workload mismatch. Many security-critical environments today are not firewalls or bastion hosts. They are distributed systems, container platforms, CI pipelines, cloud control planes, and data-processing infrastructure. Linux is the native substrate for these workloads. BSD security strengths do not map cleanly onto container-heavy or orchestration-driven models.

Fourth, security model expectations. Enterprises often want externally enforceable controls. Mandatory access control frameworks, compliance scanning, policy engines, and central enforcement matter for audits and governance. BSD security focuses on correctness, defaults, and code quality rather than administrator-authored global policy. That is effective, but harder to sell to auditors.

Fifth, hardware and firmware reality. Security-critical systems increasingly rely on modern CPUs, accelerators, NICs, TPMs, and vendor firmware. Linux receives support for these far earlier and more completely. Even if BSD is more careful, lack of timely support can itself become a security risk.

Sixth, success in narrow niches. BSD is used where its strengths align perfectly: firewalls, routers, network appliances, some embedded systems, and tightly scoped servers. In those roles it is often excellent. It is not absent from security-critical use; it is concentrated where coherence and simplicity matter more than integration breadth.

In short, BSD is not avoided because it is insecure. It is avoided because modern security-critical systems are ecosystem-heavy, automation-heavy, and vendor-driven. Linux fits that world better. BSD fits a world where you want to understand and control the whole machine, and that world is smaller than it used to be.

Is it actually deployed anywhere

Yes. BSD systems are deployed in real, production, security-relevant environments, but they tend to be either infrastructure-adjacent or embedded inside products rather than visible as general-purpose platforms.

OpenBSD itself is deployed most visibly in network security roles. It is commonly used for firewalls, VPN gateways, bastion hosts, DNS infrastructure, and other tightly scoped services where correctness, simplicity, and predictable behaviour matter more than ecosystem integration. A concrete example is OpenBSD’s own projects: OpenSSH is used almost everywhere on the internet, including on Linux systems, routers, appliances, and cloud infrastructure. That alone represents massive real-world deployment of OpenBSD-developed security code.

FreeBSD has broader industrial deployment. It is the basis of several major commercial systems. Juniper’s JunOS, which runs on a large proportion of core internet routing hardware, is built on FreeBSD. Netflix famously runs much of its content delivery network on FreeBSD because of its networking and performance characteristics. Many storage appliances and firewalls are FreeBSD-based.

NetBSD is widely used in embedded and specialised environments where portability matters, including networking gear and legacy hardware.

There is also indirect deployment. Apple’s macOS and iOS derive significant parts of their userland and networking stack from BSD, although heavily modified and wrapped in proprietary layers. Many security-relevant components in Apple platforms originate from BSD codebases.

What you do not see much anymore is BSD as the primary OS for large, heterogeneous, security-critical fleets in enterprises or cloud platforms. That space is dominated by Linux because of tooling, vendor support, and integration requirements, not because BSD failed technically.

So the accurate picture is this: BSD is deployed extensively, but selectively. It appears where people want a small, understandable base system or where it is embedded inside a product. It is less visible in modern platform-style deployments, even when the underlying security properties are strong.

Linux seems on the rise if anything.

Yes. Linux adoption continues to grow overall.

Linux is increasingly dominant in servers, cloud infrastructure, containers, edge computing, mobile (via Android), networking appliances, and enterprise environments. A few reasons for that trend are ecosystem scale, vendor support, tooling, and integration with modern development practices like containers and orchestration.

Large cloud providers build their platforms on Linux and contribute back to the kernel and tooling. Most commercial software targets Linux first or exclusively. Hardware vendors prioritise Linux drivers and firmware support. DevOps and SRE practices are built around tooling that assumes Linux as the base platform. All of this reinforces adoption momentum.

BSD systems, by contrast, tend to be chosen for specific, often narrower use cases. They remain relevant in areas where their design principles provide clear benefits, such as high-quality networking stacks, embedded systems with limited scope, or integrated products such as firewalls and routers. They do not have the same reach across general-purpose compute, cloud platforms, and container ecosystems.

In practical terms, Linux is expanding because it fits the direction of modern infrastructure: distributed systems, rapid deployment, automation, and broad hardware support. BSD’s philosophy emphasises coherence, minimalism, and auditability, which remain valuable, but these attributes do not align as directly with mainstream enterprise and cloud operational models.

So your observation that Linux is on the rise aligns with how organisations are deploying technology today. BSD systems continue to be used, but their footprint is comparatively stable or niche rather than growing at the same pace as Linux.

It seems the final markets it doesn't dominate, just a matter of time. The power of ecosystem pull is slow but relentless.

That assessment is largely correct, with one important caveat.

Ecosystem pull is indeed slow and relentless. Linux benefits from positive feedback loops that are very difficult to counter. More users lead to more vendors, which leads to better hardware support, which leads to more tooling, which leads to more trained engineers, which leads to institutional confidence. Once that cycle starts, technical merit alone rarely dislodges it.

You can see this pattern repeatedly. Linux moved from servers into networking gear, from embedded into consumer devices, from “not for desktops” into mainstream developer workstations. Android extended Linux dominance into mobile. Containers and cloud platforms then locked Linux in as the substrate for modern infrastructure. Each step reduced the remaining surface where alternatives could justify themselves.

However, there are limits to ecosystem dominance.

Linux dominates platforms and general-purpose compute. It does not dominate products. Where the goal is a tightly scoped appliance, firmware-like system, or a product whose value comes from predictability rather than extensibility, BSD-style systems still make sense. In those cases, the ecosystem is intentionally constrained. The value is not pull, but control.

There is also a cultural limit. Some projects explicitly reject ecosystem gravity because it brings complexity they consider unacceptable. OpenBSD is not losing market share accidentally. It is choosing not to compete in those markets.

So the long-term picture is probably this:

Linux will continue to absorb almost all general-purpose, scalable, and commercially integrated markets. That trend is unlikely to reverse. BSD systems will persist in niches where coherence, minimalism, and ownership of the whole stack matter more than integration and growth. Those niches will not disappear, but they will not expand much either.

In other words, Linux’s rise is real and durable. BSD’s continued existence is not a failure to compete, but a refusal to optimise for the same success criteria.

But conpablity layers are slowly falling, look at Steam.

Yes. Steam is a good example of how compatibility layers change the dynamics, but they do not eliminate ecosystem gravity. They redirect it.

Valve’s use of Proton shows that you do not need native software dominance to achieve user-facing dominance. By investing heavily in a compatibility layer, Linux gained access to a Windows-only ecosystem without persuading that ecosystem to move. From the user’s perspective, the platform gap shrinks or disappears.

However, note what actually happened architecturally.

Steam did not reduce Linux complexity. It added another layer on top of it. Proton itself is a large, fast-moving stack built on Wine, DXVK, vkd3d, Mesa, kernel features, and GPU drivers. This works because Linux is already the most aggressively layered Unix-like system. It tolerates this kind of accretion well.

The key effect is not simplification but leverage. Compatibility layers allow Linux to absorb workloads without absorbing their design constraints. Windows APIs remain Windows APIs. Linux simply becomes good enough at pretending. That reinforces Linux’s position as the universal substrate.

This does not translate cleanly to BSD.

BSD systems deliberately avoid large compatibility layers in the base system. Maintaining something like Proton would run counter to their design goals. Even Linux’s own success here depends on kernel interfaces, graphics stacks, and driver models that BSD does not replicate at the same pace or scale.

So you are right that compatibility layers are “falling” in the sense that users no longer care as much what the native platform is. But the winner of that shift is the platform most capable of hosting those layers. Right now, that is Linux.

In effect, compatibility layers accelerate convergence, but they still converge onto one dominant substrate. Steam did not weaken ecosystem pull. It demonstrated how powerful it becomes once users stop caring about what is native.

How good is wine now?

Current state of *Wine *is best described as solid but imperfect.

Wine is a compatibility layer that translates Windows API calls into POSIX calls so you can run many Windows applications on Linux (and other Unix-like operating systems) without full emulation or a VM.
WineHQ

Compatibility and breadth
Wine works quite well for many older and simpler applications, especially legacy tools and utilities whose APIs have been stable for years. Many of those run without major issues.
Reddit
+1
 For newer or complex software, especially those depending on recent Windows frameworks (for example .NET, Windows services, or intricate installers), Wine can be hit or miss and may require significant tweaking to work, or may not work at all.
Reddit
+1

Gaming support
Directly with Wine, support is reasonable, but most of the big progress in game compatibility on Linux comes from Proton, Valve’s fork of Wine tuned for gaming, with additional layers (DXVK, VKD3D, etc.) that improve DirectX support and performance.
GamingOnLinux
+1
 Proton currently allows a large majority of Windows games to run on Linux fairly smoothly (community data suggests roughly 80–90 per cent of tested titles can be played, often at near-native performance).
Tom's Hardware

Evolution and development
Development continues actively. Wine 10 and upcoming Wine 11 releases include many improvements under the hood (better driver support, updated libraries, ARM support, bug fixes).
GamingOnLinux
+1
 But compatibility is still application-specific, and you should expect some trial and error.

Tooling around Wine
Front-ends like Bottles, PlayOnLinux, and community databases like ProtonDB help users find settings and compatibility information for specific applications, reducing manual configuration.
Mastodon
+1

Overall assessment
Wine is very good for many simple and legacy Windows applications and decent for a wide range of games and heavier software with the help of Proton or other patches. It is not a guarantee that every Windows program will run, particularly complex commercial software or apps that expect deep integration with the Windows kernel or services.
Reddit
+1

So in practice:

Older and simpler apps often run well.
Reddit

Many games run well through Proton.
Tom's Hardware

Modern Windows software and business applications may require workarounds or may not run at all.
Reddit

If you need specific compatibility for particular apps you rely on, testing with Wine/Proton and community reports is the most reliable way to judge suitability.

Has it got better? Also will it more or less work for any old app now?

Yes. Wine today is significantly better than it was a decade ago, but the improvement is incremental and uneven, not universal.

General state of Wine

Wine’s compatibility has steadily improved over many years. Some areas that are objectively better now:

More complete implementation of core Windows APIs.

Better support for 32-bit and 64-bit applications.

More stable networking and graphics subsystems.

Ongoing bug fixes, updated libraries, and broader Unicode/locale support.

These improvements mean more apps run correctly out of the box now than in the past.

However, Wine is still a reimplementation of Windows behaviour. There are two consequences:

Not every Windows program runs. Some run perfectly, some run with minor glitches, some crash, and some will not start at all. There is no guarantee that “any old app” will work reliably.

Compatibility varies by application. Programs that use well-supported and stable APIs (especially older ones) are much more likely to work than modern, complex, or framework-heavy applications.

What tends to work well

Simple utilities and older Win32 apps that do not depend on lots of Windows services or modern frameworks. These often run with few or no changes.

Many Classic Windows games, especially older DirectX 7/8/9 titles.

Some mid-aged desktop software that avoids heavy integration with proprietary Windows components.

What tends to be problematic

Applications that depend on recent Microsoft frameworks like .NET (especially newer .NET Core/5/6/7+), UWP, or Windows Store packaging. Wine often has incomplete support or requires complicated workarounds.

Software with custom installers, drivers, kernel-mode components, or deep integration with Windows services.

Modern games or apps that rely on Windows APIs that are not yet fully implemented in Wine.

Role of Proton and related stacks

If your goal is games, Linux’s Proton (a fork of Wine with additional layers like DXVK and VKD3D) has transformed compatibility. Proton runs many Windows games on Linux with good performance. That success has pushed Wine development forward indirectly, but Proton itself contains significant patches and libraries not in vanilla Wine.

Status relative to “any old app”

No. Wine will not simply run any random Windows program reliably just because it exists. Many older applications work well, but:

Compatibility is app-specific.

Some require configuration, overrides, DLL replacements, or specific Wine versions.

Some never reach acceptable usability.

If you have specific applications in mind, checking current compatibility reports (e.g., Wine AppDB, ProtonDB) is the best way to judge likelihood of success.

Summary

Wine is better now than in the past.

It will run many Windows applications, especially older ones.

It does not guarantee that any Windows program will work.

Real-world results depend on the specific app and its dependencies.

But why hasn't proton improved it much?

Because Proton improves coverage far more than it improves generality, and those are different things.

Proton is highly effective because it is narrowly optimised. It targets a specific workload class: Windows games distributed through Steam, running on known Linux graphics stacks, with a controlled runtime environment. Within that scope, Valve can patch aggressively, hard-code behaviour, ship workarounds, and tolerate complexity that would be unacceptable in upstream Wine.

That success does not translate cleanly to Wine as a whole for several reasons.

First, Proton carries workload-specific hacks. Many Proton fixes are conditional on particular games, engines, or DRM behaviours. They solve “this game works” rather than “this API is now correctly implemented for all software”. Upstream Wine is cautious about accepting such patches because they increase maintenance cost and reduce conceptual correctness.

Second, Proton relies heavily on auxiliary projects. DXVK, VKD3D-Proton, fsync/esync, shader caches, and Mesa driver behaviour do a large amount of the real work. These layers bypass or replace parts of Wine’s traditional DirectX implementation. That is excellent for games, but it does not help non-graphics-heavy applications, installers, enterprise software, or Windows tooling.

Third, games tolerate different failure modes. Games are often single-process, latency-tolerant, and forgiving of subtle API inaccuracies as long as they render frames correctly. Business applications, IDEs, creative tools, and installers are much less tolerant of incorrect Windows semantics. Proton’s approach would cause regressions or undefined behaviour in those classes of software.

Fourth, Proton assumes Linux kernel features Wine cannot require. Proton depends on modern kernel primitives, scheduler behaviour, and filesystem semantics that Wine must treat as optional. Wine targets a broader range of Unix-like systems and configurations. That constraint slows down adoption of Linux-specific optimisations.

Fifth, Valve can freeze the environment. Steam controls the runtime, the libraries, the distribution path, and often the update cadence. Wine does not have that luxury. General-purpose compatibility layers must work across arbitrary distributions, library versions, and user configurations.

So Proton has improved Wine indirectly by funding development, fixing real bugs, and advancing graphics translation. But it has not turned Wine into a universal Windows compatibility layer, because that was never Proton’s goal.

In short: Proton succeeds by specialising and layering. Wine remains limited because general correctness is harder than targeted usefulness. Proton demonstrates how powerful compatibility can be when you narrow the problem space. It does not eliminate the underlying complexity of faithfully reproducing Windows.

But how good is proton

Proton is very good within its intended scope, and mediocre outside it.

Within Steam gaming, Proton is now mature enough that Linux is a viable gaming platform for many users without special effort. A large majority of Windows games on Steam run, many of them well, and a substantial subset run at near-native performance. From a practical perspective, this is a qualitative shift compared to even five years ago.

What Proton does well:

Proton excels at DirectX translation. The combination of DXVK for DirectX 9 to 11 and VKD3D-Proton for DirectX 12 is the core reason for its success. These layers translate DirectX calls to Vulkan efficiently and predictably. For GPU-bound games, performance is often comparable to Windows and occasionally better, depending on driver behaviour.

It also benefits from a controlled environment. Steam provides a fixed runtime, known library versions, and a predictable execution model. That removes many variables that normally make Wine fragile. Proton can assume modern kernels, modern Mesa or proprietary drivers, and known filesystem semantics.

Valve also invests heavily in compatibility engineering. Proton includes targeted fixes for anti-cheat, DRM, launchers, and game engines. These are not elegant solutions, but they are effective. The goal is “game runs”, not “API is perfectly implemented”.

Where Proton is weak:

Coverage is not universal. Games with kernel-level anti-cheat, invasive DRM, or unusual launch mechanisms may still fail. Multiplayer titles are overrepresented in the “broken” category, although this has improved.

Behaviour outside gaming is poor. Proton is not a general Windows runtime. Installers, productivity software, creative tools, and enterprise applications are often worse under Proton than under plain Wine, because Proton assumes game-like behaviour and tolerates hacks that would break other software.

Debuggability is limited. When something fails, fixes often involve switching Proton versions or relying on community knowledge rather than understanding the underlying cause. This is acceptable for consumers, but not for environments where predictability matters.

The bottom line:

For Steam games, Proton is good enough that platform choice is no longer a hard blocker. You can reasonably expect most popular titles to run, often without manual configuration.

For Windows software in general, Proton does not change the picture much. It is not trying to, and it should not be treated as evidence that Windows compatibility on Linux is “solved”.

So Proton is best understood as a highly specialised success. It demonstrates how powerful compatibility layers can be when the problem space is narrow, the environment is controlled, and commercial incentives exist. It does not generalise into a universal solution, and that limitation is structural, not temporary.

But other stuff a VM is fine?

Yes. For non-gaming Windows software, a VM is usually the clean, reliable solution, and in many cases it is the better solution.

For productivity software, enterprise tools, creative applications, installers, and anything with complex Windows assumptions, virtualisation avoids almost all of the pathologies of Wine and Proton. You get real Windows semantics, real drivers, real update paths, and predictable behaviour. The cost is resource overhead and some integration friction, but those trade-offs are explicit and stable.

Why VMs work well in practice:

Modern hardware support is good. With VT-x or AMD-V, performance overhead for CPU-bound workloads is small. Disk and network performance are generally acceptable. GPU acceleration is limited unless you use passthrough, but many non-graphical applications do not care.

Operationally, VMs are boring in a good way. If the application works on Windows, it will work in the VM. There is no guessing whether an API is implemented correctly, no waiting for compatibility patches, no per-app folklore.

Isolation is a benefit. Running questionable or legacy Windows software in a VM gives you strong containment. Snapshots, rollbacks, and disposable environments are trivial compared to trying to “clean up” a Wine prefix.

Where VMs are worse:

Tight desktop integration is weaker. Clipboard, file sharing, and window management are good but not seamless. If you want a Windows app to feel native, Wine or Proton can be better when they work.

Graphics-heavy workloads suffer without GPU passthrough. Games, CAD, and some creative tools are not pleasant in a VM unless you invest in passthrough, which adds complexity and hardware constraints.

Licensing and updates are real Windows problems. You still have to manage Windows itself, with its update cadence, licensing, and telemetry.

The practical rule of thumb most experienced users converge on is this:

Games: Proton first, Windows dual-boot or passthrough VM if needed.
General Windows software you depend on: VM.
Random or occasional Windows utilities: try Wine, fall back to VM.

So yes, for “other stuff”, a VM is not a cop-out. It is often the most honest solution.

Just use GPU pass through.

Yes, GPU passthrough largely removes the remaining technical objections. At that point, a Windows VM is functionally a native Windows machine that happens to live inside your Linux host.

With PCIe passthrough using VFIO, you get near-native GPU performance, proper drivers, and full compatibility. Games, CAD, video editing, and other graphics-heavy workloads behave as they would on bare metal. Latency and throughput differences are usually negligible.

What this gives you, structurally, is important:

You avoid compatibility layers entirely. No API reimplementation, no per-application quirks, no waiting for Wine or Proton fixes. If it runs on Windows, it runs. The problem space collapses to known quantities.

You get clean separation. Windows stays Windows, with its drivers, updates, and assumptions, and Linux stays Linux. Failures are contained. You can snapshot, roll back, or discard the VM without contaminating the host.

You keep Linux as the control plane. Linux handles storage, networking, automation, backups, monitoring, and scheduling. Windows becomes a workload, not the system you administrate day to day.

The trade-offs are real, but mostly upfront:

Hardware constraints matter. You typically need two GPUs, or at least a GPU plus integrated graphics. Some consumer hardware still has IOMMU quirks, broken ACS grouping, or firmware bugs.

Setup complexity is non-trivial. Initial configuration requires comfort with kernel parameters, device isolation, firmware settings, and VM tooling. Once set up, though, it is stable.

Laptop use is awkward. Passthrough is much easier on desktops and workstations. On laptops, muxed GPUs, power management, and thermal limits make this far less pleasant.

Conceptually, this is why Linux keeps winning.

Instead of chasing perfect compatibility, Linux absorbs other operating systems as guests. Wine and Proton are about convenience. VMs with passthrough are about correctness. When you have the hardware, correctness usually wins.

So yes: “just use GPU passthrough” is not flippant. It is the endgame for anyone who wants Linux as their primary system without giving up Windows-only workloads.

Is dual boot a bit redundant now

Largely, yes. For many users, dual boot is now redundant, but not universally obsolete.

For most practical workloads, Linux plus virtualisation covers the ground that dual boot used to occupy. Proton handles a large class of games. A Windows VM handles the rest, and with GPU passthrough, that VM can cover even high-performance graphics workloads. In that model, Linux is always running, and Windows is just another workload. That is a strictly more flexible arrangement than rebooting.

Dual boot’s original advantages have eroded:

Performance parity is no longer decisive. With modern virtualisation and passthrough, the performance gap is small enough to be irrelevant for most use cases.

Convenience favours virtualisation. Rebooting to switch tasks is slow, breaks workflow, and discourages integration. A VM can be paused, snapshotted, automated, or discarded.

Isolation is better with VMs. A Windows VM is easier to contain, back up, and reset than a full dual-boot install sharing firmware, disks, and bootloaders.

However, dual boot is not pointless in all cases.

There are still scenarios where it makes sense:

If you have only one GPU and no reliable passthrough option, especially on laptops. Passthrough on laptops remains awkward or impossible on many models.

If you want absolute minimum latency or maximum determinism for a specific workload and do not want to deal with passthrough complexity.

If you are constrained by licensing, corporate policy, or anti-cheat software that explicitly rejects virtualised environments.

If you want the simplest possible setup and are willing to trade flexibility for that simplicity.

So the current reality is this:

Dual boot used to be the default compromise. Now it is a fallback.

If you have suitable hardware and are comfortable with virtualisation, Linux as the host plus Windows as a guest dominates dual boot on both convenience and capability. Dual boot remains relevant mainly where hardware, policy, or simplicity force it, not because it is architecturally superior.
