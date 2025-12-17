## Context / Problem Statement

In real software systems there are **two independent dimensions of change**:

1. **Domain meaning**
   - Valid states
   - Business rules
   - Allowed transitions

2. **Interpretations of that meaning**
   - UI rendering
   - Persistence
   - Messaging, APIs, batch jobs

Object-oriented design attempted to use *objects* as the primary modelling tool for both dimensions. This worked locally, but failed to scale as systems grew.

---

## How Object Orientation Failed

### 1. Objects collapse multiple concerns

Classic OO treats an object as:
- The domain concept
- The runtime representation
- The unit of behaviour and mutation

This collapses meaning, mechanism, and execution into a single construct.

### 2. Encapsulation is local, constraints are global

Encapsulation can protect an object’s internal state, but most important constraints:
- Span multiple objects
- Span multiple layers (UI, domain, database)
- Are temporal rather than structural

OO can defend invariants at runtime, but cannot make illegal global states *unrepresentable*.

### 3. The manager object anti-pattern

To compensate, OO introduced:
- Managers
- Controllers
- Services

These centralise logic, but:
- Become god objects
- Encode workflows procedurally
- Leave domain objects anemic

They enforce rules by convention and control flow, not structure.

### 4. Only one easy dimension of change

OO primarily supports one axis of variation:
- Adding new behaviours via methods or subclasses

The other axis:
- Adding new domain cases

Requires invasive changes, is not checked exhaustively, and often fails silently.

This is the expression problem in disguise.

---

## Why ADTs Do Better

### 1. Domain as a closed set of states

Algebraic Data Types model:
- The full set of valid domain states
- Explicit alternatives
- Product and sum structure

Invalid states simply do not exist.

### 2. Invariants by construction

With ADTs:
- Values are always valid
- Transitions produce new valid values
- No partial or temporarily invalid states

Correctness is structural, not defensive.

### 3. Exhaustiveness is enforced

Pattern matching over ADTs is exhaustive:
- Add a new case → compilation fails
- The compiler enumerates every place that must change

Domain evolution is safe and explicit.

---

## Typeclasses Complete the Picture

### 1. Open interpretations with guarantees

Typeclasses allow:
- Open sets of interpretations
- Fixed required operations

Add a new method to a typeclass:
- Compilation fails
- The compiler enumerates every instance that must be updated

### 2. Two dimensions, both compiler-guided

| Dimension of change | Mechanism | Guarantee |
|--------------------|-----------|-----------|
| Domain cases | ADTs | Exhaustive handling |
| Interpretations | Typeclasses | Complete instances |

Both axes remain explicit and safe.

---

## Why This Scales

With ADTs and typeclasses:
- Domain meaning is stable and explicit
- Interpretations are replaceable
- Refactors are compiler-driven
- Illegal states are unrepresentable

The compiler becomes an active participant in maintaining correctness.

---

## Core Insight

Object orientation failed because it treated **implementation structure** as if it were **semantic structure**.

ADTs succeed because they separate:
- What is true (domain meaning)
- From what is done (interpretation)

and make both dimensions visible to the compiler.

This is the real reason ADT-based modelling yields stronger invariants and more maintainable systems.

