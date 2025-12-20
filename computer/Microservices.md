
## Core Reality

Microservices are not a UX optimisation. They are an **organisational scaling mechanism**.

## Characteristics

* Networked services with bespoke APIs
* High operational overhead: discovery, auth, observability, retries
* Expensive failure modes: partial failure, latency, timeouts
* Rarely useful or understandable in isolation

## Distributed Systems Tax

Microservices inherently introduce:

* Synchronisation complexity
* Latency amplification
* Version skew
* Debugging via indirect tooling

This is pure cost from a system-design perspective.

## Design Assessment

Microservices are **almost always a worse technical design** than a cohesive, single deployable system.

They become justified only when:

* Teams cannot safely coordinate changes
* Independent deployment is mandatory
* Ownership and blast-radius boundaries outweigh simplicity

## Key Insight

Synchronising services should be treated as a **necessary evil**, not a best practice.

## Heuristic

* One team, one deployable: microservices are likely a mistake
* Forced distribution: minimise boundaries and design defensively

## Conclusion

Microservices trade system simplicity and developer UX for organisational survivability. Invoking [[UNIX]] to justify them is usually cargo culting and a category error.
