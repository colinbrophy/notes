## What Python Optimises For

Python is optimised for **clarity, flexibility, and ease of integration**, not for static guarantees or sealed binaries.

Two design choices dominate everything else:

### 1. Reference Counting

CPython uses **reference counting** for memory management.

What this gives Python:

* Deterministic object lifetimes
* Predictable cleanup (`__del__`, file closing, resource release)
* Very simple and reliable C interop

This made it easy to write native extensions and is the reason the scientific ecosystem (NumPy, SciPy, PyTorch, etc.) exists.

The trade-off:

* Object lifetimes are observable
* Moving garbage collectors are impractical
* Many aggressive runtime optimisations are blocked

---

### 2. Ultra‑Dynamic Dispatch

Python allows almost everything to be changed at runtime:

* operator overloading
* monkey‑patching
* dynamic attribute access
* late binding everywhere

This makes Python:

* extremely flexible
* easy to introspect
* easy to adapt and glue systems together

The trade-off:

* weak static guarantees
* runtime errors instead of compile‑time errors
* difficult to optimise or compile aggressively

---

## What This Makes Python Good For

### Automation Beyond Bash

Python is ideal when a Bash script becomes:

* too complex
* too stateful
* too error‑prone
* too hard to test

Python keeps scripting lightweight while giving:

* real control flow
* proper error handling
* libraries for files, networking, JSON, HTTP

It is the natural successor to Bash for serious automation.

---

### Data, Science, and ML Glue

Python is excellent as a **control and orchestration language**:

* data pipelines
* experiments
* ML training scripts
* analysis notebooks

Python usually does *not* do the heavy computation itself.
That work happens in native code.

Python provides:

* readability
* fast iteration
* expressive pipelines

---

## What Python Is Bad At

Python has **poor raw performance**, **cannot be effectively JIT-compiled**, and **does not produce portable native binaries**.

This is a direct result of its design:

* ultra-dynamic dispatch prevents aggressive optimisation
* reference counting blocks many runtime transformations
* the runtime and native extensions cannot be cleanly bundled

As a result, Python is a poor choice for:

* performance-critical systems
* high-throughput or low-latency services
* infrastructure and long-lived backends
* tools that need to ship as a single executable

Outside of scripting, automation, and data-oriented glue code, Python’s trade-offs usually dominate.

---

## Dependencies and Packaging (Briefly)

Python’s dependency model is **environment‑based**, not artifact‑based.

Key points:

* pip installs into environments, not into locked builds
* native extensions make portability hard
* there is no clean, built‑in “build a single binary” story

In practice, this means:

* environments or containers are expected
* Docker is often used to freeze the runtime

---

## Summary Mental Model

Python is best understood as:

* a scripting language that scales past Bash
* a glue language for fast native code
* a human‑first control layer

It trades static structure and easy deployment for:

* flexibility
* clarity
* integration power

Used inside its design envelope, Python is extremely effective.
Used outside it, the costs show quickly.
