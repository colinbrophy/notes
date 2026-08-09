#ai-written

# Why Arbitrary Formal Systems Are Mostly Uninteresting

## The tempting picture

It is easy to imagine the space of small formal systems as a vast unexplored mathematical universe.

Take a few symbols and rules. Iterate them. Because even tiny Turing machines, cellular automata and rewriting systems can behave unpredictably, perhaps arbitrary formal systems are densely packed with deep new mathematics.

But this picture confuses the size of the syntactic space with the amount of distinct, fruitful mathematical structure inside it.

The space of possible rule sets is enormous. The space of genuinely interesting mathematical ideas appears to be much sparser.

## Most syntactic variation is duplication

One mathematical process has infinitely many formal presentations.

We can:

- rename states or symbols;
- add unused rules;
- split one operation into several intermediate steps;
- reverse conventions;
- introduce redundant variables;
- compile the same process into a different formalism.

Thus many formally different systems express the same semantic behaviour.

$$
\text{formal descriptions}
\gg
\text{distinct behaviours}
\gg
\text{fruitful mathematical structures}.
$$

The first space is inflated by encoding choices. Counting rule sets therefore greatly exaggerates how many genuinely different ideas are present.

The issue is not just that exact duplicates exist. Large families of systems may all reduce to minor variants of the same broad mechanism:

$$
\text{loops},\quad
\text{counters},\quad
\text{rewriting},\quad
\text{finite-state control},\quad
\text{simple recurrences}.
$$

## Nontrivial organisation is sparse

A random collection of low-level rules is unlikely to coordinate itself into a meaningful mathematical process.

To encode something such as a search for a number-theoretic counterexample, the system must reliably implement:

- representations of integers;
- arithmetic operations;
- iteration;
- conditional branching;
- tests for the required property;
- a meaningful stopping condition.

Many pieces must cooperate correctly. That is engineering.

Most arbitrary rule sets instead:

- halt quickly;
- enter simple loops;
- repeat familiar mechanisms;
- generate undirected or uninterpretable behaviour;
- or fail to preserve enough structure to perform a coherent computation.

There are infinitely many encodings of any given theorem, but this does not make them common. Each encoding belongs to a highly constrained region of rule space.

The hierarchy is roughly:

$$
\text{all formal systems}
\supset
\text{persistent systems}
\supset
\text{coherent computations}
\supset
\text{mathematically meaningful computations}.
$$

Each step narrows the space substantially.

## Complexity is easier to generate than meaning

A rule system can be difficult to predict without encoding a deep mathematical idea.

Its apparent complexity may arise from:

- inefficient representation;
- long nested loops;
- interacting counters;
- huge transient behaviour;
- complicated local implementation of a simple recurrence.

This creates a crucial distinction:

$$
\text{hard to analyse}
\neq
\text{deep}
\neq
\text{fruitful}.
$$

Skelet #1 is a useful warning. It required enormous effort to understand, but its behaviour ultimately reduced to counters, slowly changing gaps, collisions and eventual periodic motion.

The achievement was largely reverse engineering. The underlying mathematics was much less exotic than the raw behaviour suggested.

So formal difficulty can come from obfuscation rather than conceptual depth.

## Universality does not rescue the space

A sufficiently expressive formalism can encode arbitrary computation.

This is true of:

- Turing machines;
- rewriting systems;
- cellular automata;
- group word problems;
- Diophantine equations;
- differential equations;
- various physical systems.

But universality is an extremely coarse property.

If two systems are both universal, that tells us that each can imitate any computation. It does not tell us that their natural objects, mechanisms or useful theories have much in common.

Universal systems contain all computable questions, but most individual descriptions do not naturally express interesting ones.

A universal programming language can represent every great scientific theory. That does not make the set of arbitrary programs a scientific theory in its own right.

$$
\boxed{\text{The ability to encode everything does not make everything densely present in a useful form.}}
$$

## Why random axioms do not usually create subjects

An arbitrary axiom system may be:

- inconsistent;
- too weak to say much;
- a disguised version of a familiar theory;
- computationally universal but structurally unorganised;
- or an isolated system requiring special tricks.

Even when its consequences are difficult, understanding them may yield little reusable machinery.

A mathematical subject becomes fruitful when many objects share:

- natural maps;
- invariants;
- subobjects and quotients;
- decomposition methods;
- common constructions;
- classification questions;
- links to other structures.

Group theory is not valuable merely because group axioms have complicated consequences. It is valuable because the same concepts organise enormous families of examples, and theorems build on one another.

Random rules mostly generate cases. Natural structure generates theory.

## Mathematical axioms are less arbitrary than they appear

A theory such as Peano arithmetic is formally presented as symbols and axioms, which can make it resemble an arbitrary rule set.

But the axioms were chosen to isolate an already recognised structure:

- zero;
- successor;
- addition;
- multiplication;
- induction.

The notation and exact axiomatisation are partly conventional. The underlying organisation is not.

PA is a compressed description of arithmetic, not a random point in axiom space.

Likewise, the basic definitions of groups, topological spaces and vector spaces were selected because they capture patterns recurring throughout mathematics.

Mathematicians do not normally pick random axioms and hope that something fertile appears. They identify a family of phenomena and then formulate the structure that makes their shared behaviour visible.

$$
\boxed{\text{Axioms are usually coordinates on structure, not arbitrary generators of it.}}
$$

## Why focused mathematical questions make sense

The raw space of formal systems is:

- enormous;
- highly redundant;
- dominated by trivial or familiar behaviour;
- and sparse in coherent, reusable structure.

Searching it blindly is therefore a poor way to find mathematics.

The productive strategy is to restrict attention to natural classes:

- groups rather than arbitrary operation tables;
- context-free grammars rather than arbitrary rewriting rules;
- smooth dynamical systems rather than arbitrary transition functions;
- number-theoretic equations rather than arbitrary symbol strings.

These restrictions are not artificial limitations. They concentrate attention on regions where results can accumulate.

A good mathematical subject is a dense region of relationships inside a sparse formal universe.

## The lesson of Skelet

Skelet #1 is not important because it reveals a hidden continent of alien mathematics.

It is important because it shows how misleading raw formal complexity can be.

A tiny rule set can:

- resist analysis for decades;
- run through an astronomical transient;
- look chaotic;
- and still reduce to familiar low-level mechanisms once decoded.

It is therefore a cautionary tale against treating arbitrary complexity as evidence of depth.

## Conclusion

The space of formal descriptions is vast, but much of that vastness comes from duplication, triviality and obfuscation.

Meaningful mathematical systems require coordinated structure. Fruitful subjects require something stronger still: concepts and theorems that transfer across many objects.

$$
\boxed{
\text{Formal possibility is abundant.}
\qquad
\text{Fruitful structure is sparse.}
}
$$

This is why mathematics is organised around natural objects and specific questions rather than the blind exploration of random axioms.

The goal is not to find rules with complicated consequences. It is to find structures in which understanding accumulates.

Related: [[Structured Turing Machines and Mathematical Structure]], [[What Makes a Mathematical Field Interesting or Sustainable?]], [[Why Do Some Mathematical Structures Matter?]], [[Do not infer depth from omission]].
