# Fuchsia (operating system)

#ai-written #draft

## What it is

- An open-source, general-purpose operating system (not a Linux distro) that targets modern 64-bit Intel (x86_64) and ARM (AArch64) devices.
- Originated at Google as a “new stack” OS: its own kernel (Zircon) plus a user-space built around a component model.

## How to think about it (extra context)

- **Component-first architecture:** software is built/deployed as components, and components get access to resources via explicitly routed capabilities (a “least privilege” bias).
- **Microkernel-style split:** a small kernel + lots of functionality in user space (services, drivers, etc.), rather than putting everything in one big kernel.
- **Practical goal:** a modern, updatable platform for a range of device types (especially embedded/consumer), with strong isolation and reproducible builds/tooling.

## Source excerpt (fuchsia.dev)

> Fuchsia is an open source, general purpose operating system supporting modern 64-bit Intel and ARM processors.
>
## Pointers

- https://fuchsia.dev/ (overview)
- https://fuchsia.dev/fuchsia-src/get-started/ (getting started)
- https://fuchsia.dev/fuchsia-src/concepts/ (concepts / principles)
