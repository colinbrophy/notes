## Learning Checklist

### Stance

Use zsh as the interactive shell and Bash as the scripting shell.

- Do not learn zsh as a second scripting language.
- Most shell knowledge already transfers from Bash: quoting, pipelines, redirection basics, command substitution, variables, conditionals, loops, functions, jobs, and exit statuses.
- Learn zsh only where it changes daily prompt behaviour or explains `.zshrc`.
- Read the zsh manual as lookup material, not cover-to-cover.

### Actually read

This is the real reading list for interactive zsh. Do not read the parent chapters unless a listed subsection sends you there.

- [x] `5.1 Startup/Shutdown Files` - read which files are sourced when; keep `.zshenv` minimal and put interactive setup in `.zshrc`.
- [x] `16.1 Specifying Options` - learn `setopt`/`unsetopt`; then only look up the options listed below.
- [ ] `20.2 Initialization` - understand `autoload -Uz compinit` and `compinit`.
- [ ] `20.3 Completion System Configuration` - understand `zstyle` basics, menus, grouping, and matcher lists.
- [ ] `19 Completion Widgets` - skim enough to understand what happens when pressing Tab.
- [ ] `18.2 Keymaps` - know where vi/emacs mode and keymaps fit.
- [ ] `18.3 Zle Builtins` - read enough for `bindkey` and invoking widgets.
- [ ] `18.6 Standard Widgets` - look up widgets you bind, especially `edit-command-line`.
- [ ] `13 Prompt Expansion` - read prompt escapes only if customising prompts yourself.
- [ ] `14.7.2 Static named directories` - named path shortcuts.
- [ ] `14.7.3 '=' expansion` - expand command names to their full path.
- [ ] `14.8.1 Glob Operators` - zsh glob syntax, especially with `EXTENDED_GLOB`.
- [ ] `14.8.4 Globbing Flags` - per-pattern flags such as case-insensitive matching.
- [ ] `14.8.6 Recursive Globbing` - recursive matching with patterns like `**/`.
- [ ] `14.8.7 Glob Qualifiers` - filter matches by file type, size, age, permissions, etc.
- [ ] `15.2 Array Parameters` - read only the differences from Bash arrays: 1-indexing, subscripts, slices.
- [ ] `15.6 Parameters Used By The Shell` - read `$path`/`$PATH`, `$fpath`, and other config-facing parameters.
- [ ] `26.3 Remembering Recent Directories` - read if using zsh's built-in directory navigation helpers.

### Options worth looking up

Do not read every option. Look these up when they appear in `.zshrc` or affect interactive behaviour.

- Globbing: `NOMATCH`, `NULL_GLOB`, `EXTENDED_GLOB`, `GLOB_DOTS`, `BARE_GLOB_QUAL`.
- Word splitting and Bash surprises: `SH_WORD_SPLIT`, `KSH_ARRAYS`.
- Directory movement: `AUTO_CD`, `AUTO_PUSHD`, `PUSHD_IGNORE_DUPS`, `CDABLE_VARS`.
- Completion: `AUTO_MENU`, `MENU_COMPLETE`, `AUTO_LIST`, `COMPLETE_IN_WORD`, `ALWAYS_TO_END`.
- History: `HIST_IGNORE_DUPS`, `HIST_IGNORE_SPACE`, `HIST_REDUCE_BLANKS`, `SHARE_HISTORY`, `INC_APPEND_HISTORY`.
- Correction: `CORRECT`, `CORRECT_ALL`.

### Gotchas to remember

These are higher value than reading more manual pages.

- `.zshenv` is sourced very broadly; do not put slow or interactive-only setup there.
- Prompt syntax is zsh `%` escapes, not Bash `PS1` backslash escapes.
- Zsh arrays are 1-indexed by default.
- Zsh does not do Bash-style word splitting by default.
- Unmatched globs error by default via `NOMATCH`.
- Use glob qualifiers like `(N)` or options like `NULL_GLOB` intentionally; do not assume Bash's unmatched-glob behaviour.
- Zsh has much richer globbing; use it interactively, avoid it in scripts.
- Aliases expand early; use functions when aliases get weird.
- `$path` and `$PATH` are tied; zsh has array versions of some colon-separated variables.
- `$fpath` controls where autoloaded functions and completion functions are found.
- Completion is a whole system, not just a Bash-style add-on.

### Lookup only when customising `.zshrc`

Use these only when a config snippet, plugin, prompt, or completion function makes them relevant.

- `5.2 Files` - zsh support/config file lookup.
- `6.2 Precommand Modifiers` - `noglob` to disable globbing for one command.
- `6.8.1 Alias difficulties` - why aliases can behave unexpectedly.
- `9.1 Autoloading Functions` - loading functions from `$fpath`.
- `14.2 Process Substitution` - especially zsh's `=(...)` real-temporary-file form.
- `14.3.1 Parameter Expansion Flags` - compact string/list transformations used in prompts and config.
- `15.5 Parameters Set By The Shell` - special parameters useful in prompts and config.
- `17 Shell Builtin Commands` - `setopt`, `autoload`, `zstyle`, `bindkey`, and `emulate`.
- `18.5 User-Defined Widgets` - custom commands bound to keys.
- `20.8 Completion Directories` - where completion functions live.
- `22 Zsh Modules` - only when a function/plugin asks for one.
- `26.4 Abbreviated dynamic references to directories` - extra directory shortcuts.
- `26.5 Gathering information from version control systems` - useful when building your own prompt.
- `26.6 Prompt Themes` - useful if not using an external prompt tool.
- `26.7 ZLE Functions` - packaged helper functions for the line editor.

### Skip because Bash covers it

These are not worth relearning through zsh while Bash is the scripting target.

- [ ] `4.1 Invocation` - except startup-file details covered by `5.1`.
- [ ] `4.2 Compatibility` - only look up if using zsh emulation modes.
- [ ] `4.3 Restricted Shell`
- [ ] `6 Shell Grammar` - simple commands, lists, pipelines, compound commands, loops, conditionals, and functions.
- [ ] `7 Redirection` - skip basics; look up zsh redirection extras only if needed.
- [ ] `8 Command Execution` - expansion order, command lookup, environment, status, traps/signals.
- [ ] `9 Functions` - skip general function syntax except `9.1 Autoloading Functions`.
- [ ] `10 Jobs & Signals` - same interactive job-control basics.
- [ ] `11 Arithmetic Evaluation`
- [ ] `12 Conditional Expressions`
- [ ] `14 Expansion` - do not read the whole chapter; only read `14.7` and `14.8` for interactive use, plus lookup items above.
- [ ] `15 Parameters` - do not read the whole chapter; only read config-facing differences listed above.

### Optional later / lookup only

- [ ] `6.4 Alternate Forms For Complex Commands` - recognise zsh shorthand syntax; do not adopt for scripts.
- [ ] `7.1 Opening file descriptors using parameters` - zsh-specific fd allocation style.
- [ ] `7.2 Multios` - redirect output to multiple places.
- [ ] `7.3 Redirections with no command` - zsh-specific shorthand.
- [ ] `9.2 Anonymous Functions`
- [ ] `9.3 Special Functions`
- [ ] `14.7.1 Dynamic named directories`
- [ ] `14.8.2 ksh-like Glob Operators` - only relevant if `KSH_GLOB` is enabled.
- [ ] `14.8.5 Approximate Matching`
- [ ] `26.2 Utilities`
- [ ] `26.8 Exception Handling`
- [ ] `26.9 MIME Functions`
- [ ] `26.10 Mathematical Functions`
- [ ] `26.11 User Configuration Functions`
- [ ] `26.12 Other Functions`

### Legacy / niche

`compctl` is the old completion interface. Modern zsh completion is built around `compinit` and the compsys framework.

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
