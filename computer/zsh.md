## Learning Checklist

### Stance

Use zsh as the interactive shell and Bash as the scripting shell.

- Learn zsh where it is zsh-only or materially different from Bash: startup files, options, completion, prompt, history, line editing, navigation, globbing/expansion, and `.zshrc`.
- Do not learn zsh as a scripting language for now.
- For scripts, prefer `#!/usr/bin/env bash` and Bash/POSIX habits.
- Read the zsh manual as a delta from Bash, not as a second shell-programming manual.
- Treat "zsh-only" and "worth learning now" as different filters: some zsh-only systems are niche.

### Reading filter

- Learn now: zsh-only or zsh-different behaviour that affects daily interactive use.
- Notice/reference: zsh-only features that are powerful but only needed when customising `.zshrc` deeply.
- Skim/skip: generic shell grammar and scripting concepts already covered by Bash.
- Ignore for now: obsolete, niche, or documentation-administration material.

### Learn now - interactive core

- [ ] `5.1 Startup/Shutdown Files` - know where config belongs; keep `.zshenv` minimal and put interactive config in `.zshrc`.
- [x] `16 Options` - behaviour toggles for globbing, completion, history, and Bash-compat surprises.
- [ ] `18 Zsh Line Editor` - ZLE, widgets, keybindings, vi/emacs mode, `bindkey`, `edit-command-line`.
- [ ] `19 Completion Widgets` - how completion behaves at the prompt.
- [ ] `20 Completion System` - `compinit`, styles, matchers, menus, and completion function locations.
- [ ] `13 Prompt Expansion` - zsh prompt `%` escapes; enough to customise prompts or understand prompt frameworks.
- [ ] `14 Expansion` - interactive parts: history expansion, filename generation, glob operators, recursive globbing, glob qualifiers, named directories, `=` expansion, and expansion surprises.
- [ ] `15 Parameters` - only zsh differences that appear in config: arrays, subscripts, special parameters, tied parameters like `PATH`/`path`, and `FPATH`/`fpath`.
- [ ] `26.3 Remembering Recent Directories` - faster directory navigation.

### Zsh-only / zsh-different feature map

These are bookmarks for zsh-specific features, not a second reading pass. If the parent chapter is already in the interactive core list, treat the subsection as something to notice while reading that chapter.

Config/loading:

- `5.2 Files` - reference for zsh support/config files once `.zshrc` grows.
- `9.1 Autoloading Functions` - how zsh loads functions from `$fpath`, including completion functions.
- `20.8 Completion Directories` - where zsh completion functions live.
- `17 Shell Builtin Commands` - reference for zsh config builtins such as `setopt`, `autoload`, `zstyle`, `bindkey`, and `emulate`.
- `22 Zsh Modules` - loadable features; use only when a plugin/function asks for one.

Command-line syntax and aliases:

- `6.2 Precommand Modifiers` - `noglob` to disable globbing for one command.
- `6.4 Alternate Forms For Complex Commands` - zsh shorthand syntax; recognise, do not adopt for scripts.
- `6.8.1 Alias difficulties` - alias expansion happens early; use functions when aliases get weird.

Redirection extras:

- `7.1 Opening file descriptors using parameters` - zsh-specific fd allocation style.
- `7.2 Multios` - redirect output to multiple places.
- `7.3 Redirections with no command` - zsh-specific shorthand; reference only.

Expansion/globbing:

- `14.2 Process Substitution` - Bash has `<(...)`; zsh also has `=(...)` when a command needs a real temporary file.
- `14.3.1 Parameter Expansion Flags` - powerful string/list transformations, especially in prompts and config.
- `14.7.1 Dynamic named directories` - directory shortcuts generated dynamically.
- `14.7.2 Static named directories` - named path shortcuts.
- `14.7.3 '=' expansion` - expand command names to their full path.
- `14.8.1 Glob Operators` - zsh glob syntax, especially with `EXTENDED_GLOB`.
- `14.8.2 ksh-like Glob Operators` - recognise if `KSH_GLOB` is enabled; do not use as default style.
- `14.8.4 Globbing Flags` - per-pattern flags such as case-insensitive matching.
- `14.8.5 Approximate Matching` - tolerate typos in glob/completion matches.
- `14.8.6 Recursive Globbing` - recursive matching with patterns like `**/`.
- `14.8.7 Glob Qualifiers` - filter matches by file type, size, age, permissions, etc.

Parameters:

- `15.2 Array Parameters` - zsh array and subscript rules that differ from Bash.
- `15.5 Parameters Set By The Shell` - special parameters useful in prompts and config.
- `15.6 Parameters Used By The Shell` - shell-controlled parameters such as `path`, `fpath`, and history/prompt variables.

Prompt, completion, and line editor:

- `18.5 User-Defined Widgets` - custom interactive commands bound to keys.
- `18.7 Character Highlighting` - highlight text in the line editor.
- `26.4 Abbreviated dynamic references to directories` - more directory-navigation shortcuts.
- `26.5 Gathering information from version control systems` - useful when building your own prompt.
- `26.6 Prompt Themes` - useful if not using an external prompt tool.
- `26.7 ZLE Functions` - packaged helper functions for the line editor.

### Bash-to-zsh gotchas

- `.zshenv` is sourced very broadly; do not put slow or interactive-only setup there.
- Prompt syntax is zsh `%` escapes, not Bash `PS1` backslash escapes.
- Zsh arrays are 1-indexed by default.
- Zsh does not do Bash-style word splitting by default.
- Unmatched globs error by default via `NOMATCH`.
- Use glob qualifiers like `(N)` or options like `NULL_GLOB` intentionally; do not assume Bash's unmatched-glob behaviour.
- Zsh has much richer globbing; use it interactively, avoid it in scripts.
- Aliases can be weird because expansion happens early; see `6.8.1 Alias difficulties` if this bites.
- `$path` and `$PATH` are tied; zsh has array versions of some colon-separated variables.
- `$fpath` controls where autoloaded functions and completion functions are found.
- Completion is a whole system, not just a Bash-style add-on.

### Skim or skip - Bash covers this

These are useful shell concepts, but not worth relearning through zsh while Bash is the scripting target.

- [ ] `4.1 Invocation` - skim only for zsh-only flags.
- [ ] `4.3 Restricted Shell`
- [ ] `6 Shell Grammar` - simple commands, lists, pipelines, compound commands, loops, conditionals, functions; only read zsh extras listed above.
- [ ] `7 Redirection` - skip the basics; only read zsh extras listed above.
- [ ] `8 Command Execution` - expansion, command lookup, environment, status, traps/signals.
- [ ] `9 Functions` - skip general function syntax until writing non-trivial `.zshrc` helpers; see `9.1` above for autoloading.
- [ ] `10 Jobs & Signals` - same interactive job-control basics.
- [ ] `11 Arithmetic Evaluation`
- [ ] `12 Conditional Expressions`

### Optional later - zsh-specific but not daily

- [ ] `4.2 Compatibility` - Bash/sh/ksh emulation and divergences.
- [ ] `9.2 Anonymous Functions`
- [ ] `9.3 Special Functions`
- [ ] `26.2 Utilities`
- [ ] `26.8 Exception Handling`
- [ ] `26.9 MIME Functions`
- [ ] `26.10 Mathematical Functions`
- [ ] `26.11 User Configuration Functions`
- [ ] `26.12 Other Functions`

### Legacy / niche

- `compctl` is here because modern zsh completion is built around `compinit` + the compsys framework (`20 Completion System`). `compctl` still exists, but it is the older interface.

- [ ] `21 Completion Using compctl`
- [ ] `23 Calendar Function System`
- [ ] `24 TCP Function System`
- [ ] `25 Zftp Function System`

### Don't read cover-to-cover

Manual front matter and indexes are lookup tools, not learning targets.

- [ ] `1 The Z Shell Manual`
- [ ] `1.1 Producing documentation from zsh.texi`
- [ ] `2 Introduction`
- [ ] `2.1 Author`
- [ ] `2.2 Availability`
- [ ] `2.3 Mailing Lists`
- [ ] `2.4 The Zsh FAQ`
- [ ] `2.5 The Zsh Web Page`
- [ ] `2.6 The Zsh Userguide`
- [ ] `2.7 See Also`
- [ ] `3 Roadmap`
- [ ] `Concept Index`
- [ ] `Variables Index`
- [ ] `Options Index`
- [ ] `Functions Index`
- [ ] `Editor Functions Index`
- [ ] `Style and Tag Index`
