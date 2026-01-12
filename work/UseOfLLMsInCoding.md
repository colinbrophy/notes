**The friction reality:**
- GUI friction is invisible but compounds
- LLM friction is worse: hallucination, lost context, verification tax, re-prompting
- Natural language is harder to learn than CLI by orders of magnitude—unbounded, no spec, shifts underneath you. CLI is finite and knowable.

**Where LLMs are genuinely faster (even for the CLI/neovim wizard):**
- Idea exploration
- Translation (where no deterministic transpiler exists; includes docs)
- Semantic transforms beyond regex/LSP
- Spot explanations in unfamiliar code
- Deep lookup (well-documented tools, poorly indexed by intent—the ffmpeg problem)

**The discipline:**
- Don't use LLMs for what your tools can do
- Skill atrophy is worse here than with autocomplete—you lose the skill AND the replacement is unreliable
- METR study: devs were 19% slower on familiar codebases with AI, while believing they were faster

**The pattern:**
The LLM is a narrow tool for specific gaps where verification is cheap. For everything else, the CLI/neovim user is faster and more reliable. The people who think LLMs remove the need to learn tools have it exactly backwards—the LLM is a lookup accelerator for people who already know what good looks like.

Related: [[Tacit knowledge]].
