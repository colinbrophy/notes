

## Completion

| Key | Widget | Action |
|-----|--------|--------|
| `TAB` | `expand-or-complete` | Complete |
| `M-^D` | `list-choices` | List completions |

## Misc

| Key    | Widget              | Action                              |
| ------ | ------------------- | ----------------------------------- |
| `^L`   | `clear-screen`      | Clear screen                        |
| `^G`   | `send-break`        | Abort                               |
| `^V`   | `quoted-insert`     | Insert next char literally          |
| `^X^E` | `edit-command-line` | Edit in $EDITOR (requires autoload) |

`^` = Ctrl, `M-` = Alt (or Esc prefix)

## Learning Checklist

Use zsh as the interactive shell and Bash as the scripting shell. For now, only learn zsh for interactive use: completion, prompt, history, line editing, navigation, globbing, and `.zshrc`. Skip generic shell grammar unless zsh behaves differently.

For scripts, prefer `#!/usr/bin/env bash` and Bash/POSIX habits over zsh-specific syntax. Zsh knowledge is mainly for the command line and `.zshrc`.

### What to actually learn

Learn zsh as an interactive command-line UI, not as a scripting language. Also know what the cool stuff is, so it is available when a command-line annoyance appears.

Interactive core:

- [ ] `5.1 Startup/Shutdown Files` - know which file does what; mostly put interactive config in `.zshrc`.
- [x] `16 Options` - learn options that change interactive behaviour, especially globbing, completion, history, and Bash-compat surprises.
- [ ] `18 Zsh Line Editor` - command-line editing, widgets, keybindings, vi/emacs mode, `bindkey`, `edit-command-line`.
- [ ] `19 Completion Widgets`
- [ ] `20 Completion System` - `compinit`, completion styles, matchers, menus, and completion function locations.
- [ ] `13 Prompt Expansion` - enough to customise prompts or understand prompt frameworks.
- [ ] `14 Expansion` - only enough to understand interactive expansion surprises.
- [ ] `26.3 Remembering Recent Directories` - useful for faster navigation.

Cool stuff to know exists, excluding items already in the interactive core list:

- [ ] `14.8.7 Glob Qualifiers` - filter matches by file type, size, age, permissions, etc.
- [ ] `14.8.6 Recursive Globbing` - use `**` patterns for tree-wide matches.
- [ ] `14.8.5 Approximate Matching` - tolerate typos in glob/completion matches.
- [ ] `14.7.1 Dynamic named directories`
- [ ] `14.7.2 Static named directories` - shortcuts for important paths.
- [ ] `14.7.3 '=' expansion` - expand command names to their full path.
- [ ] `14.3.1 Parameter Expansion Flags` - powerful transformations at the prompt; do not build scripts around them for now.
- [ ] `7.2 Multios` - redirect output to multiple places.
- [ ] `18.4 User-Defined Widgets` - custom interactive commands bound to keys.
- [ ] `26.5 Gathering information from version control systems` - only if building your own prompt.
- [ ] `26.6 Prompt Themes` - only if building your own prompt.

Main Bash-to-zsh differences to watch for:

- Zsh arrays are 1-indexed by default.
- Zsh does not do Bash-style word splitting by default.
- Unmatched globs error by default via `NOMATCH`.
- Zsh has much richer globbing; use it interactively, avoid it in scripts.
- Aliases can be weird because expansion happens early.
- `$path` and `$PATH` are tied; zsh has array versions of some colon-separated variables.
- Completion is a whole system, not just a Bash-style add-on.

Skip unless needed:

- Full shell grammar.
- Command execution model.
- Job control basics.
- Arithmetic.
- Most builtins.
- Restricted shell.
- `compctl`.
- Zsh as a scripting language.

### Bash already covers this - skim/skip for zsh

These map closely onto Bash scripting knowledge. Since Bash is the scripting target, don't spend much zsh time here except to notice interactive differences.

- [ ] `4.1 Invocation` - same job as Bash invocation; skim for zsh-only flags.
- [ ] `4.3 Restricted Shell` - same concept as Bash restricted shell.
- [ ] `6 Shell Grammar` - mostly the same grammar: simple commands, lists, pipelines, compound commands, loops, conditionals, functions.
- [ ] `7 Redirection` - same baseline redirection model: `<`, `>`, `>>`, `2>`, descriptor duplication, here-docs, here-strings.
- [ ] `8 Command Execution` - same broad model: expansion, command lookup, environment, status, traps/signals.
- [ ] `9 Functions` - same basic function idea; read only the zsh-specific subsections below.
- [ ] `10 Jobs & Signals` - same interactive job-control concepts: jobs, foreground/background, signals.
- [ ] `11 Arithmetic Evaluation` - same shell arithmetic role.
- [ ] `12 Conditional Expressions` - same `[[ ... ]]` style tests with zsh-specific operators worth skimming.
- [ ] `17 Shell Builtin Commands` - many familiar builtins; use as reference, not cover-to-cover reading.

### Learn for interactive zsh

These are either zsh-specific, substantially richer in zsh, or common sources of Bash-to-zsh surprises at the interactive prompt.

- [ ] `4.2 Compatibility` - which Bash/sh/ksh behaviours zsh emulates and where it does not.
- [ ] `5.1 Startup/Shutdown Files` - `.zshenv`, `.zprofile`, `.zshrc`, `.zlogin`, `.zlogout` differ from Bash startup files.
- [ ] `5.2 Files` - reference for zsh's config and support files.
- [ ] `6.2 Precommand Modifiers` - `noglob`, `exec`, `command`, `builtin`, etc.
- [ ] `6.4 Alternate Forms For Complex Commands` - zsh's extra shorthand forms.
- [ ] `6.8.1 Alias difficulties` - aliases expand early and can surprise you.
- [ ] `7.1 Opening file descriptors using parameters`
- [ ] `7.2 Multios` - zsh can redirect one stream to multiple files/processes.
- [ ] `7.3 Redirections with no command`
- [ ] `9.2 Anonymous Functions`
- [ ] `9.3 Special Functions`
- [ ] `13 Prompt Expansion` - zsh prompt escapes and conditional prompt syntax.
- [ ] `14 Expansion` - high-value section; zsh expansion differs a lot from Bash.
- [ ] `14.3.1 Parameter Expansion Flags`
- [ ] `14.7.1 Dynamic named directories`
- [ ] `14.7.2 Static named directories`
- [ ] `14.7.3 '=' expansion`
- [ ] `14.8.5 Approximate Matching`
- [ ] `14.8.6 Recursive Globbing`
- [ ] `14.8.7 Glob Qualifiers`
- [ ] `15 Parameters` - zsh parameter attributes, arrays, tied parameters.
- [ ] `15.2 Array Parameters` - zsh arrays are 1-indexed by default; this is a Bash difference worth learning.
- [ ] `16 Options` - zsh behaviour is option-heavy; many Bash-like behaviours are toggles.
- [ ] `16.3 Option Aliases`
- [ ] `16.4 Single Letter Options`
- [ ] `18 Zsh Line Editor` - zle replaces Bash/readline as the main editing model.
- [ ] `18.7 Character Highlighting`
- [ ] `19 Completion Widgets`
- [ ] `20 Completion System` - modern zsh completion: `compinit`, styles, matchers, functions.
- [ ] `20.8 Completion Directories`
- [ ] `22 Zsh Modules` - only as needed.
- [ ] `26.2 Utilities`
- [ ] `26.3 Remembering Recent Directories`
- [ ] `26.4 Abbreviated dynamic references to directories`
- [ ] `26.5 Gathering information from version control systems`
- [ ] `26.6 Prompt Themes`
- [ ] `26.7 ZLE Functions`
- [ ] `26.8 Exception Handling`
- [ ] `26.9 MIME Functions`
- [ ] `26.10 Mathematical Functions`
- [ ] `26.11 User Configuration Functions`
- [ ] `26.12 Other Functions`

### Lazy learn - mostly legacy / niche in 2026

- `compctl` is here because modern zsh completion is built around `compinit` + the compsys framework (`20 Completion System`). `compctl` still exists, but it is the older interface and most current configs, examples, and third-party completion definitions assume compsys instead.

- [ ] `21 Completion Using compctl`
- [ ] `23 Calendar Function System`
- [ ] `24 TCP Function System`
- [ ] `25 Zftp Function System`

### Don't learn

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
