# Types, Languages, and Real‑World Software

## Context
Discussion about why some languages feel *professionally correct* while others produce fragile, slow, and over‑engineered systems. Focus on Go, OCaml, Haskell, and why strong type systems matter only for certain classes of software.

---

## Core Thesis

- Bugs are not inevitable; they are largely a consequence of **weak modelling, weak types, and sales‑driven practices**.
- Strong type systems dramatically reduce bugs **only when the problem has deep structure**.
- Many so‑called "robust practices" (OO inheritance, manager objects, default [[Microservices]]) are cargo cults that *reduce* correctness and speed.

---

## Where Strong Type Systems Are Essential

Strong typing is not about elegance; it is about **tractability**.

### High‑leverage domains
- DSLs
- Compilers and interpreters
- Document transformers (e.g. Pandoc)
- Protocols and state machines
- Meaning‑dense, transformation‑heavy software

Why:
- Input space is combinatorial and effectively infinite
- Tests cannot cover structural correctness
- Forgotten cases produce silent semantic bugs

Here:
- Algebraic data types
- Exhaustiveness checking
- Compiler‑guided refactors

are *necessary*, not optional.

Pandoc is a canonical example where Haskell’s type system is decisive.

---

## Where Strong Types Help Less

### CRUD, CLIs, networking glue
- Mostly I/O bound
- Shallow domains
- Failures are acceptable and visible

In these cases:
- Invariants live in the database or the OS
- Explicit checks are sufficient
- Operational simplicity dominates

Go excels here.

---

## Language Roles (Pragmatic)

### Go
- Best for CLIs, services, networking
- Fast startup
- Single static binary
- Boring, predictable ops
- Weak modelling, but excellent UX and reliability

### OCaml
- Best balance of correctness and pragmatism
- ADTs + exhaustiveness encode invariants
- Predictable runtime
- No npm‑style dependency chaos

### Haskell
- King of DSLs and abstraction‑heavy systems
- Extra type power pays off only in meaning‑dense software
- Slower startup, heavier runtime

### Rust / C / Zig
- Systems programming
- High development pain
- Usually minimal user‑visible benefit for services

### TypeScript
- UI and boundary language
- Teaches modelling under uncertainty
- Practical, unavoidable

---

## ADTs vs Encapsulation

### Encapsulation (OO)
- Controls access, not meaning
- Invariants are informal and temporal
- Broken easily by inheritance
- Leads to manager objects

### ADTs
- Encode invariants structurally
- Closed world of states
- Exhaustiveness enforced by compiler
- No manager objects required

Encapsulation manages behaviour.
ADTs encode truth.

---

## Manager Objects Are a Smell

- Appear when invariants cannot be expressed in types
- Centralise logic and knowledge
- Create tight coupling
- Become brittle over time

They are not good design; they are **workarounds for missing language features**.

---

## Testing vs Types

- Tests sample the input space
- Types *close* the input space

Property testing is useful **only** for:
- Semantic laws
- Round‑tripping
- Behavioural equivalences

It is not a substitute for strong structural typing.

Dependent types are usually not worth the cost.

---

## Why the Industry Is Buggy and Slow

- Sales incentives reward demos, not correctness
- Complexity is profitable
- Frameworks replace modelling
- Engineers are rarely taught invariants or ADTs

Weak correctness culture produces:
- Fragile systems
- Slow refactors
- Defensive runtime code
- Bureaucratic processes

Poor correctness also makes software *slower* in practice.

---

## Final Mental Model

Use the right language for the job:

- **Meaning** → Haskell
- **Correctness‑critical logic** → OCaml
- **User‑facing execution and ops** → Go
- **UI and product surface** → TypeScript

Robust systems are boring.
If nothing interesting happens, the design is probably good.

