Below is the **eager-learning list**: commands and concepts that pay off **only if learned up front**. These remove constant lookup friction and unlock composition. Everything not listed here is better learned _just-in-time_.

This is intentionally small.

---

## 1. Shell semantics (non-negotiable)

Learn these _before_ memorising commands.

- Pipes and redirection: `|`, `>`, `>>`, `<`, `2>`, `&>`
- Quoting rules: `'...'`, `"..."`, `$()`
- Exit codes and `set -e`, `&&`, `||`
- Globbing vs regex
- Subshells and command substitution

If this is weak, every tool is painful.

---

## 2. Core process control

These eliminate hesitation when things go wrong.

- `jobs`, `fg`, `bg`
- `kill`, `killall`
- `wait`
- `nohup`, `&`

You should not need to think about these.

---

## 3. Files and paths (automatic)

- `ls`, `cd`, `pwd`
- `cp`, `mv`, `rm`, `ln`
- `stat`, `file`
- `find` (especially predicates and `-exec`)

This is the physical layer of Unix.

---

## 4. Text and stream algebra (this is the real core)

Learn these **for composition**, not flags.

- `cat`, `less`
- `grep` (regex fundamentals)
- `sed` (simple substitutions only)
- `awk` (fields, patterns, actions)
- `sort`, `uniq`
- `cut`, `tr`
- `wc`
- `xargs`

If you know these well, most other tools collapse into one-liners.

---

## 5. Modern but essential additions

These are not historical Unix, but they _fix modern reality_.

### Search and navigation

- `rg`
- `fd`
- `fzf`

### Structured data

- `jq`  
    Learn only:
    - `.foo.bar`
    - `.items[]`
    - `select(...)`
    - `map(...)`
    - `-r`

This restores composability to JSON.

---

## 6. System visibility (conceptual + muscle memory)

- `ps`
- `top` or `htop`
- `df`, `du`
- `lsof`
- `journalctl`
- `dmesg`

You should know _when_ to reach for each without thinking.

---

## 7. Minimal system control

Learn the model, not the flags.

- `mount`, `umount`
- `systemctl` (start, stop, status, enable)
- `ip` (address, link, route at a high level)
- `ss`
- `curl`

This is the boundary between userland and the system.

---

## 8. Editing and history

These multiply everything else.

- `vim` (motions, operators, macros)
- Shell history and reverse search
- `git` (commit graph, rebase, bisect, blame)

Not optional.

---

## Explicitly _not_ on the eager list

Do **not** pre-learn:

- Filesystem repair tools
- TPM, crypto, SELinux, audit tooling
- Package manager internals
- Hardware diagnostics
- Media, PDF, TeX toolchains
- Desktop helpers
- Daemons and service binaries

These are lookup tools by design.

---

## Size of the real core

If you count _actual commands_, this is about **35–45** items.

If you count _ideas_, it is closer to **10**: streams, text, processes, files, composition.

That is the stable centre. Everything else is peripheral.