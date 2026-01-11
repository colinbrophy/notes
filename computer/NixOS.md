# NixOS

#draft #ai-written

## One-line model

- NixOS treats the operating system as a **built artifact**: a single declarative configuration is evaluated into a bootable system “generation”, rather than a mutable system being incrementally changed into shape.

## What NixOS gives you (that `stow` + Ansible + Fedora don’t)

### A single, declarative description of the whole OS

- One configuration describes packages, services, systemd units, kernel choices, users, filesystems, bootloader, etc.
- The “real system” is intended to be fully explained by the config, not by the machine’s history.

### Atomic upgrades and “real” rollbacks

- Switching from one system generation to the next is transactional: you either activate the new generation or keep the previous one.
- Rollback is selecting a previous generation (often from the boot menu), not “reconstruct whatever state used to be true”.

### Hermetic dependency closures (coexisting versions)

- Packages and dependencies live in an immutable store with exact paths, so multiple versions of the same library can coexist.
- This reduces the “something upgraded underneath me” class of problems and makes runtime dependencies more explicit.

### Reproducibility across time (“time travel”)

- A pinned `nixpkgs` revision + your config defines a system strongly enough that you can rebuild “what I had then” later.
- In practice: cloning machines and recreating old environments tends to be much more reliable than replaying old imperative setup steps on a newer distro release.

### Fewer bespoke glue steps for services

- Enabling a service is typically “turn the module on and set options”; the system derives unit files, config, dependencies, and wiring.
- The model is closer to “describe intent” than “run these steps”.

## What Fedora + Ansible + `stow` already gives you

- Excellent dotfile hygiene (`stow`) and repeatable setup steps (Ansible) on a familiar, mutable base system.
- A workflow that favors ad-hoc experimentation: install/tweak/test/undo quickly, then codify later if it’s worth keeping.
- “Boring upgrades” if you maintain the machine well (which makes a lot of NixOS’s usual reliability pitch irrelevant).

## New pain NixOS can introduce (especially with a well-run Fedora setup)

- Cognitive overhead: Nix language + nixpkgs conventions + modules (and maybe flakes/overlays) before things feel ergonomic.
- Indirection: many “normal files” are generated; paths are hashed and immutable; debugging often starts with “what did my config evaluate to?”.
- Friction for tinkering: quick one-off changes are discouraged; you’re nudged toward editing config + rebuilding for things that used to be a 5-minute experiment.
- More failure modes: evaluation-time vs build-time vs activation-time vs runtime errors can make failures feel abstract.
- Occasional upstream mismatch: software that assumes FHS paths, mutable `/usr`, or writable `/etc` can require overrides/patches you’d never notice on Fedora.
- Payoff is backloaded: it can feel like pure overhead until the model “clicks”.

## A practical heuristic

- If your machine currently feels like a reliable tool, NixOS can turn it into a project.
- If you want the system itself to be a versioned, reproducible artifact you can diff/rollback/clone, NixOS offers something categorically different from “better automation”.

## Low-commitment ways to try the model

- Use the Nix package manager on Fedora for isolated dev tooling without changing the host OS model.
- Try NixOS in a VM and see whether the “generation” workflow actually makes your life better.

