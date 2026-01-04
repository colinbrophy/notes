---
tags: [draft, ai-written]
---

## Context / goal

Capture questions about why NixOS can feel “high overhead” for simple installs/experiments compared to Homebrew or Ansible, and why immutable/declarative approaches are preferred for servers despite the friction.

## Key points

- Nix/NixOS records “intent” declaratively; the overhead is translating ad-hoc experiments into explicit config.
- Homebrew makes many CLI installs trivial and ubiquitous across macOS (and some Linux/WSL usage), but some tools prefer fast self-updates (example: `yt-dlp`) and may outpace package-manager update cadence.
- “Image and restore” is less popular for servers because it preserves undocumented mutation; infra-as-code aims to prevent configuration drift and capture intent.
- Ansible has lower mental overhead than Nix for many tasks because it stays close to the imperative model while still recording desired state.
- Desktop workflows often favour quick mutations and avoiding disruptive steps (e.g., reboots) even if that sacrifices perfect reproducibility.

## Cleanup targets

- [[NixOS]]
- [[Nix]]
- [[Homebrew]]
- [[Ansible]]
- [[Terraform]]
- [[configuration drift]]
- [[declarative vs imperative]]
- [[yt-dlp]]

## Chat (verbatim)

What is it about NixOS's design that makes the overhead he talks about here.
So stuff that is just a simple brew install becomes what?
Almost all CLI tools have brew support too. It supports Mac, Linux and WSL with no work from devs side. So it tends to be everywhere, especially as it's the main way on Mac.
Ans some tools just want to self update for good reason.
yt-dlp is a good one, needs fast updates
yt-dlp suggests you download and let it self update even over bew.
Even homebrew is too slow.
why is it then that for servers, imaging and backing them up is less popular than terraform, ansible or the NIX approach?
accumulate undocumented mutations.

So the core issue is lack or recording of intent? This is a maintence pain?
The cost of writing down intent for every experiment is higher than the cost of occasional breakage.

The cost is acualtly quite low with ansible vs Nix OS
Ansible is a thin layer on top of the imperitive model and is more high level than NIX so is less painful.
In truth you want to be able to do quick mutations on a desktop. Nobody want to reboot for an update.
