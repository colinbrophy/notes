#ai-written 

# TTY and Unix Design Notes

## What a TTY actually is

A TTY is a kernel-managed communication channel between processes and something that looks like a terminal. Three pieces:

1. **TTY driver** — handles job control (foreground/background, who gets input)
2. **Line discipline** — handles cooked/raw mode, `^C` → SIGINT translation, basic line editing
3. **The device** — either real hardware (rare) or a pty pair

## Pseudo-terminals (pty)

A pty is a pipe with TTY magic in the middle:

- **Master** — held by terminal emulator (xterm, kitty, tmux)
- **Slave** (`/dev/pts/N`) — what your shell sees as "the terminal"

Terminal emulator writes keystrokes to master → kernel delivers to slave → shell reads them. Output goes the reverse direction.

## /dev/tty and friends

|Device|What's on the other end|
|---|---|
|`/dev/ttyS0`|Physical serial hardware|
|`/dev/tty1`|Kernel's built-in VT emulator|
|`/dev/pts/3`|A terminal emulator process|
|`/dev/tty`|"Whichever of the above is mine" (magic shortcut)|

## Process states

|State|Meaning|
|---|---|
|R|Running/runnable — actually doing work|
|S|Interruptible sleep — waiting, will wake for signals|
|D|Uninterruptible sleep — stuck on I/O, can't be killed|
|T|Stopped — paused by `^Z` or debugger|
|Z|Zombie — finished but parent hasn't reaped|

R and S are the main ones. D means something's wrong with I/O. Z means buggy parent.

**Reaping:** When a process exits, it leaves a stub with its exit status. Parent calls `wait()` to collect it and let kernel delete the stub. Until then, it's a zombie.

## Sessions and process groups

**Session** = everything that should die together when the terminal disconnects.

**Process group** = a job, things that should be controlled together (one pipeline, one `^C`).

```
Session
├── Process group 101 (bash) ← session leader
├── Process group 102 (cat &) ← background job  
└── Process group 103 (ls | sort) ← foreground job
```

tmux "sessions" are different — a tmux session contains multiple Unix sessions (one per pane).

## What's in the kernel vs bash

**Kernel:**

- `^C` sends SIGINT, `^Z` sends SIGTSTP
- Line editing in cooked mode (backspace, `^U`, `^W`)
- Echo, foreground/background tracking
- Suspending background jobs that try to read/write terminal

**Bash:**

- Prompt, command parsing, history, tab completion
- `jobs`, `fg`, `bg`, `disown` commands
- Setting up process groups for pipelines
- Readline's fancier editing (after putting TTY in raw mode)

Test: run `cat` with no arguments — backspace works. That's the kernel, not cat.

## What Unix got right

- TTY as "the user" — one device any process can grab
- Everything outputs to one place — you don't lose output
- Sessions and process groups — clean "what dies together" model
- Job control UX — `^Z`, `fg`, `bg`, `&` — simple and works
- Silence on success — no news is good news

## What's just cruft

- Line discipline in kernel (could be userspace)
- Signals for everything (crude)
- UART settings on fake terminals
- The tangled layers of backwards compatibility

## A cleaner design would use

- **cgroups** for process groups — already exists, cleaner hierarchy
- **Userspace line editing** — shell/readline handles it
- **Userspace job control** — shell tracks foreground, routes input
- **Separate user channel** — dedicated fd for "the human", not stdin/stdout

Same capabilities, less kernel involvement.

## CLI tool design

**Tools that work with shared TTY (line-oriented):** grep, sed, awk, cat, find, jq, ripgrep, compilers

**Tools that break (assume screen ownership):** vim, htop, less, fzf, anything curses-based

**Progress bars are bad:**

- Break concurrent output
- Can't be logged or piped
- Hide errors
- Use cursor hacks

Better: silence on success, verbose flag when you need details, `pv` for one-off throughput checks.

## "Everything is a file" — not really

**Actually files:** /dev (mostly works as file abstraction)

**Awkwardly shoehorned:** /proc, /sys — inconsistent formats, fragile parsing, not meant as user-facing API

**Not files at all:** signals, ioctl, fork/exec, sockets, memory mapping

Honest version: "files where convenient, something else where not."

## The cult problem

Two failure modes:

1. Dismissing Unix — throws out the good with the bad
2. The cult — defends cruft as genius, gatekeeps, treats 1970s constraints as sacred

The philosophy is good heuristics, not religion. Pragmatism over purity.