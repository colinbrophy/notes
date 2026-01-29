
## Context

UNIX is often invoked in modern software discussions, especially to justify architectural choices like [[Microservices]]. 

## Core Idea

UNIX is fundamentally a **UX principle** aimed at humans using computers.

Text is the fundamental principle, as a universal data format. 

We are not discovering new fundamental categories of information every five years. Text, numbers, time series, images, graphs, hierarchies, relationships. What changes is the operations on said data. UNIX says the data must be simple open formats, so new programs can be written for it.

## Key Characteristics

* Programs are **directly usable by humans** via CLI tools
* Each tool does one thing well and is **independently meaningful**
* **Text streams** (stdin/stdout) provide a universal, inspectable interface
* Composition happens **interactively** via pipes
* Debugging is trivial: run tools in isolation, insert `cat` or `tee`, inspect output

## Why It Works

* Single machine, single failure domain
* Near-zero IPC cost
* Clear, synchronous execution model
* Failures are local, visible, and understandable

## UX Emphasis

UNIX optimises for:

* Learnability
* Discoverability
* Inspectability
* Human-scale reasoning

This framing is reinforced by 1980s UNIX advertising, which explicitly sold UNIX as *easier to use*.

## LLMs

LLMs fit the UNIX model best when treated as **stateless filters**:

* `stdin` is the authoritative context (man page, `--help`, official docs, source)
* `stdout` is a concise answer/extraction
* if the answer is not in the text: `not found` (don’t guess)

This is a practical way to avoid search/SEO sludge and reduce hallucination by forcing grounded extraction.

See: [[LLMs]]

## Conclusion

UNIX improves developer experience at the point of use. Its benefits disappear when the human operator is removed from the loop.
