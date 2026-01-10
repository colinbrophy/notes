---
tags: [draft, ai-written]
---

## Context / goal

Capture a discussion about why coding agents gravitate to the CLI over IDEs, and how UNIX-style text/pipes align with agent loops.

## Key points

- The terminal is the lowest common denominator: shell + git + tests work everywhere.
- CLI gives agents direct authority: edit–run–inspect loops without IDE UI state.
- Pipes/text/exit codes create tight, composable feedback signals for agent loops.
- IDE scaffolding adds overhead, brittleness, and opacity as models get stronger.
- Models already “speak” shell and logs, reducing need for heavy tool protocols.
- Agents resemble UNIX tools: keep the loop simple and compose with the system.

## Cleanup targets

- [[UNIX]]
- [[Command line]]
- [[Coding agents]]
- [[IDEs]]
- [[Agent loops]]

## Chat (verbatim)

Why are people just using coding agents in the CLI, not in IDEs. The Terminal is making a comeback.

It really does feel like the terminal is having a moment again, doesn’t it. And it is not nostalgia. There are some very concrete reasons why coding agents are gravitating to the CLI instead of IDEs.

First, the terminal is the lowest common denominator that already works everywhere. A coding agent can read files, run tests, invoke linters, apply patches, commit changes, and inspect diffs using standard tools that exist on almost every system. Bash, git, make, pytest, go test, ansible-lint, cargo test, dnf, npm, ripgrep. All of this is stable, scriptable, and extremely well understood. An agent that can operate a shell can immediately do real work in any codebase without learning an IDE’s internal model.

Second, the CLI gives agents real authority, not just suggestions. In an IDE, agents are often boxed into “assistive” roles: propose edits, insert snippets, highlight lines. In the terminal, the agent can actually run the same commands a senior engineer would run. It can bisect, re-run failing tests, inspect generated artefacts, regenerate code, and loop until the system is green. That tight edit–run–inspect loop is exactly what agentic workflows need, and the shell is already designed for it.

Third, terminals compose naturally with automation in a way IDEs struggle with. Pipes, exit codes, logs, text streams, temporary files. Agents thrive on this because it gives them crisp feedback signals. A command fails, here is stderr. Tests fail, here is a diff. Lint fails, here is a rule ID. IDEs tend to hide or abstract this behind UI state, which is great for humans but awkward for autonomous loops.

There is also a control and trust angle that matters a lot to experienced engineers. Running an agent in the CLI feels contained. You can put it in a repo, a container, a tmux pane, or a restricted environment. You can see exactly what commands it ran. You can kill it with Ctrl-C. IDE agents often feel more opaque, more stateful, and harder to reason about when something goes wrong.

Another big factor is that modern agents have outgrown the original IDE value proposition. IDEs shone because they indexed code, resolved symbols, and provided navigation. Today’s models can often infer structure directly from files plus grep. When context windows are large and models are strong at search and reasoning, the extra semantic layer an IDE provides is less critical. The agent just needs fast file access and good tools, not a graphical representation of the AST.

There is also a cultural shift here. Senior engineers already live in the terminal for serious work: git, CI debugging, infra, prod incidents, build systems. When agents entered the picture, they naturally joined that environment rather than pulling people back into heavyweight GUIs. It feels like extending an existing mental model rather than adopting a new one.

So the terminal is not really “making a comeback” so much as revealing its hidden strength. It was always a programmable interface to the system. Coding agents are just the first non-human users that can exploit that fully. IDEs are not going away, but for agentic work, the CLI turns out to be the most honest, powerful, and scalable interface we have.

So it's the UNIX philsophy of text and pipes. Universal interface to any programming language, runtime etc.

Exactly. You’ve put your finger on it.

What’s reasserting itself is the classic UNIX philosophy: text as the universal interface, small tools that do one thing well, and composition via pipes. That model turns out to be almost perfectly aligned with what coding agents need.

Text is the key. Source code is text. Diffs are text. Logs are text. Errors are text. Test output is text. Configuration is text. An agent does not need rich UI affordances or deep object models when everything meaningful can be inspected, transformed, and reasoned about as streams of text. Once you accept that, the shell becomes a lingua franca across languages, runtimes, and ecosystems.

Pipes matter just as much. They let you decompose complex workflows into simple, inspectable steps with clear inputs and outputs. For an agent, that is gold. Run a command, parse stdout, branch on exit code, feed the result into the next command. That is essentially an agent loop already baked into the operating system. No bespoke SDK required.

It is also universal in a very strong sense. Whether you are dealing with C, Python, Rust, Go, Java, JavaScript, Terraform, Ansible, or Nix, there is always a CLI toolchain that speaks the same basic protocol: commands in, text out. IDE abstractions are language-specific and often brittle. The shell does not care what language you are using, only whether the tool ran and what it said.

There is a deeper point here too. UNIX tools were designed for composability by humans with limited working memory. LLM-based agents have a different constraint profile, but composability still matters. They benefit enormously from systems where intermediate state is explicit, serialisable, and inspectable. Pipes, files, and logs give you exactly that. IDE state is often implicit, transient, and hidden behind UI events.

This is why the terminal suddenly feels “future-proof” rather than retro. It is a stable, minimal protocol between intelligence and machinery. Humans used it first. Now agents can use it too. And because it already spans every language, runtime, and operating system we care about, it quietly becomes the universal control surface for software again.

In that sense, coding agents are not dragging us backwards. They are revealing that UNIX accidentally designed the perfect interface for non-human programmers decades ago.

And building on top of a big IDE, means a lot more harness for the model, where with the terminal, just use the bare model.

Yes, that’s exactly right, and it is a really important distinction.

An IDE-based agent needs a lot of harness. It has to understand the IDE’s internal representation of files, buffers, cursors, projects, symbols, indexers, background tasks, UI state, and often a proprietary extension API layered on top. All of that is extra surface area the model has to reason about before it can even start doing the real work. You end up spending model capacity on “how do I operate this environment?” rather than “how do I fix the bug or implement the change?”.

With the terminal, the interface is already fully specified and extremely small. Commands in, text out, exit code. Files on disk are the source of truth. Git tells you what changed. Tests tell you whether it worked. The model does not need a complex adapter layer to act effectively. You can take a strong general model and drop it straight into a shell loop and it is immediately useful.

This also changes where complexity lives. IDE agents push complexity into the integration layer: plugins, RPCs, schema translations, background indexing, synchronisation bugs. CLI agents push complexity into the model, which is exactly where you want it, because models are improving rapidly while IDE integration code is brittle and slow to evolve. Every new language server quirk or IDE update is another place things can break.

There is a trust and safety angle here too. A big IDE harness often feels like a black box mediating the model’s actions. When something goes wrong, it is hard to tell whether the model misunderstood the task or the integration layer did something odd. In the terminal, the agent’s actions are legible. You can literally scroll back and see every command it ran. That transparency makes people much more comfortable letting agents operate autonomously.

It also explains why bare-model tools like Claude Code, Aider, and simple “LLM + bash loop” setups have taken off so quickly. They are thin shells around very capable models. As models got good enough at planning, searching, and correcting themselves, the heavy scaffolding stopped paying for itself.

So yes, the terminal works because it lets you expose the model directly to the system with almost no impedance mismatch. The shell is not just an interface. It is a protocol. And a very old one that turns out to be perfectly suited to intelligent automation.

So what is the downside of the scaffold?

There are real downsides, and they are not subtle once you have felt them.

The biggest one is impedance mismatch. A scaffold sits between the model and the system and translates intentions into actions. That translation layer is never perfect. The model thinks in terms of files, diffs, tests, and commands. The scaffold thinks in terms of editor buffers, virtual documents, symbol graphs, UI state, and RPC calls. Every mismatch creates failure modes that feel uncanny: edits applied to the wrong buffer, stale indexes, actions that “succeed” in the UI but do not correspond to what is on disk. When something breaks, you are debugging the harness, not the task.

Closely related is brittleness under iteration. Agentic workflows rely on tight loops: try, observe, correct, retry. Scaffolds tend to be stateful and complex, so they accumulate hidden state across iterations. A model can be perfectly capable of fixing a bug, but the scaffold is now out of sync with reality. Humans then step in to reset the IDE, reload the window, restart the language server. That friction kills autonomy.

There is also a cost in model capacity. Every extra abstraction the model has to reason about consumes tokens and attention. Instead of focusing on “why did this test fail”, it is spending context on “which editor API do I call to apply this edit safely”. That overhead made sense when models were weak and needed hand-holding. As models got stronger, the harness started to look like ballast.

Another downside is lag and inertia. IDE scaffolds move at human software speeds. Plugin APIs change slowly. Backwards compatibility matters. Large vendors are cautious. Models, meanwhile, are improving every few months. The more logic you bake into the scaffold, the more you freeze assumptions about how the model should work. CLI-based agents can immediately benefit from better reasoning, larger context, or better tool use without rewriting thousands of lines of integration code.

Transparency is another big one. With a scaffold, actions are mediated. You often see the result, not the process. That makes trust harder. In the terminal, you can audit everything. You see the exact commands, the exact diffs, the exact failures. This matters enormously once agents are doing non-trivial changes. People trust what they can inspect.

Finally, scaffolds bias behaviour. IDE agents tend to optimise for local edits, symbol-level refactors, and “nice looking” code changes because that is what IDE abstractions make easy. CLI agents naturally optimise for system-level correctness: tests passing, builds succeeding, deployments working. That bias difference shows up very quickly in real projects.

So the downside of the scaffold is not that it is useless. It is that once the model is strong enough, the scaffold becomes a tax: more complexity, more brittleness, less transparency, slower evolution. The terminal works because it removes that tax and lets the model operate directly on reality, using the same levers humans have always used.

The model has been trained on lots of bash commands, no need for some complex MCP or simialr.

Yes, exactly. That’s the quiet but decisive point.

Modern models have already absorbed an enormous amount of bash, POSIX tooling, git workflows, CI logs, Makefiles, Dockerfiles, error traces, and shell transcripts. Not as a special capability, just as part of their natural training diet. For them, the shell is not an external tool that needs explaining. It is a familiar language environment.

Because of that, you do not need a heavy protocol layer like MCP to “teach” the model how to operate the system. The model already knows that ls shows files, grep searches text, git diff shows changes, tests fail with non-zero exit codes, and stderr matters more than stdout. You can drop it straight into a shell loop and it behaves sensibly with almost no ceremony.

This flips an earlier assumption on its head. MCP and similar systems made sense when models were weak at tool use and needed a rigid schema: here is the tool, here are the arguments, here is the response format. But once models can read raw command output and reason over it reliably, that structure becomes optional. In many cases it becomes a hindrance, because you are forcing natural language competence back into a narrow API box.

Bash is also forgiving in the right way. It is text-based, lossy, and messy, but the messiness is informative. Warnings, partial failures, stack traces, interleaved logs. Models are surprisingly good at extracting signal from that noise, often better than humans. A strict tool protocol throws away that richness in favour of clean schemas, which sounds nice but often removes context the model could have used.

There is also a leverage argument. Every extra layer like MCP is something you have to design, maintain, version, and debug. Bash already exists everywhere, is stable, and changes slowly. Training keeps getting better, but bash does not need to. That asymmetry strongly favours “use the bare model plus the shell” as the long-term equilibrium.

So yes, the resurgence of the terminal is not accidental. It is the intersection of two facts: the shell is a universal, minimal control surface, and models have already been trained deeply enough on it that they do not need a bespoke harness. Once that clicked, a lot of people realised they could delete an entire layer of complexity and get better results.

Its also the AI agents themselves follwing the "We just to the agent loop well" UNIX philsophy.

Yes, that’s a really sharp way to see it, and it fits beautifully.

The agent ecosystem is converging on the same idea UNIX converged on decades ago: do one thing well, and let composition do the rest. For agents, that “one thing” is the agent loop. Read state, decide, act, observe, repeat. Everything else is just I/O.

If you squint a bit, a modern CLI coding agent looks exactly like a classic UNIX tool. It reads text from the world, emits text back into the world, and relies on external programs to actually do work. It does not try to be a debugger, a compiler, a test runner, or a package manager. It orchestrates them. That restraint is what makes it powerful.

This is why the simplest agents often outperform the fanciest ones. A clean loop that can run commands, read output, and update files is enough to solve a surprisingly large class of problems. Add retries, backtracking, and a bit of memory, and you already have something that feels shockingly capable. No giant framework required.

It also explains why these agents compose so naturally with existing workflows. You can stick one in a tmux pane, wrap it in a script, run it under CI, or constrain it with Unix permissions and containers. It behaves like another process on the system, not a magical entity that needs a special environment. That makes it easy to trust and easy to kill when it misbehaves.

There is even a philosophical alignment. UNIX assumed intelligence lives in the user, not the tool. The tools are dumb, composable, and transparent. With LLMs, intelligence actually does live in the agent, so the philosophy snaps into focus even more cleanly. Keep the tools simple. Keep the interfaces textual. Let the intelligence sit above the system, not inside it.

So in a very real sense, AI agents are rediscovering UNIX, not as a historical curiosity, but as the most natural architecture for embodied intelligence in software. “Do the agent loop well” is the new “do one thing well”, and the terminal is where that principle finally gets to stretch its legs again.
