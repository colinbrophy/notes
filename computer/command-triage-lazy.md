# Reference command catalogue

These tools are outside the current stack or do not justify scheduled study. Use documentation, `--help`, or examples if a real task calls for them.

## Git
- [ ] `jj` (Jujutsu) is a Git-compatible version-control system with first-class change tracking and automatic working-copy commits
- [ ] `git-absorb` automatically creates `fixup!` commits by matching staged changes to earlier commits
- [ ] tuicr
- [ ] `ghq` clones and manages many repos under one directory
- [ ] `hunk` provides review-first terminal diffs for agent-authored changesets
- [ ] Worktrunk and similar worktree managers
- [ ] https://blog.jcoglan.com/2017/05/08/merging-with-diff3/
- [ ] [Sapling](https://github.com/facebook/sapling)
- [ ] `gitk` GUI log
- [ ] `gh-dash` terminal dashboard for GitHub pull requests and issues

## Modern CLI replacements
- [ ] `ast-grep` searches and rewrites code by syntax structure rather than plain text
- [ ] `rga` / `ripgrep-all` searches PDFs, Office docs, archives, and other rich files with ripgrep-like ergonomics
- [ ] `difft` / Difftastic provides syntax-aware structural diffs ([GitHub](https://github.com/Wilfred/difftastic))
- [ ] `hyperfine` benchmarks commands properly
- [ ] `eza`: modern `ls` replacement
- [ ] `bat`: cat with syntax highlighting and git integration
- [ ] `yazi`: file browser tui
- [ ] `fzf-tab`: zsh plugin for fzf-powered tab completion
- [ ] `fzf-tmux`: fzf inside tmux panes
- [x] `atuin`: much better shell history/search
- [ ] autin ai setup i
- [ ] `gum`: build polished interactive shell script prompts and menus
- [ ] `btop`: gorgeous process/resource monitor
- [x] `ncdu`: interactive disk usage explorer — find what's eating space
- [x] `lazygit`: TUI git client you already use
-  pull requests?
- [x] `tree`: directory tree view

## AWS
- [ ] `aws-vault` provides safer AWS credential handling
- [ ] `granted` switches AWS accounts, profiles, and assumed roles

## Databases / cache
- [ ] `redis-cli` supports Redis inspection and debugging
- [ ] `sqlite3` inspects and queries SQLite databases

## Systemd / logs
- [ ] `systemctl`: service/unit management (`status`, `list-units`, `cat`, `edit`, `daemon-reload`)
- [ ] `journalctl`: log viewer (`-u`, `-b`, `-f`)
- [ ] `oomctl` inspects systemd-oomd state
- [ ] `rtcwake` suspends/hibernates until a scheduled wake time
- [x] `timedatectl`: time/timezone/NTP state
- [x] `shutdown` schedules or triggers shutdown/reboot on modern systemd systems
- [x] `reboot` triggers an immediate reboot
- [x] `poweroff` powers the system down immediately
- [x] `halt` halts the machine; usually prefer `systemctl poweroff`

## Docs / discovery
- [ ] `navi` provides interactive, searchable command cheatsheets

## File operations
- [ ] `rename` batch-renames files
- [ ] `trash-cli` provides a safer interactive deletion workflow than raw `rm`

## Permissions / identity / access
- [x] `umask`: default permissions for newly created files
- [x] `getfacl`: view POSIX ACLs
- [x] `setfacl`: set POSIX ACLs
- [x] `namei`: follow path components and permissions
- [x] `getcap`: view file capabilities
- [x] `setcap`: set file capabilities
- [x] `runuser`: run command as another user, often from root scripts

## Checksums / encoding / binary inspection
- [x] `sha256sum`: verify file hash
- [x] `sha512sum`: verify file hash
- [ ] `rhash`: compute many hash formats
- [x] `base64`: encode/decode base64
- [x] `xxd`: hex dump / reverse hex dump
- [x] `hexdump`: inspect binary data
- [x] `od`: byte/word dumps with precise numeric formatting
- [x] `strings`: extract printable strings from binaries

## Terminal / TTY
- [ ] `asciinema` records terminal sessions
- [ ] `agg` turns asciinema recordings into GIF/video
- [ ] `vhs` scripts terminal demos and recordings

## System info
- [x] `uname`: system info
- [x] `hostname`: hostname
- [x] `hostnamectl`: inspect/set system hostname and related metadata
- [x] `uptime`: load/uptime
- [x] `free`: quick memory + swap usage
- [x] `vmstat`: fast CPU, memory, I/O, and run queue snapshot
- [x] `lscpu`: CPU topology and virtualization flags
- [x] `lsmem`: memory layout/topology
- [x] `nproc`: number of available processing units
- [x] `date`: date/time
- [x] `cal`: calendar
- [x] `who`: logged in users
- [x] `whoami`: current user
- [x] `id`: user/group IDs
- [x] `groups`: group membership
- [x] `env`: environment variables
- [x] `printenv`: print env vars

## Login/session/account state
- [x] `last`: login history
- [x] `lastlog`: last login per user
- [x] `w`: logged-in users + what they are doing
- [x] `logname`: original login name
- [x] `newgrp`: switch current group

## Disk/filesystem
- [x] `df`: disk free space
- [x] `du`: disk usage
- [x] `mount`: mount filesystems
- [x] `umount`: unmount
- [x] `mountpoint`: check whether a path is a mountpoint
- [x] `lsblk`: block device list
- [x] `blkid`: filesystem UUIDs/types
- [x] `findmnt`: show mount tree
- [x] `smartctl`: disk SMART health checks
- [x] `cryptsetup`: LUKS disk encryption
- [x] `fdisk`: classic disk partition editor
- [x] `fsck`: check/repair filesystems
- [x] `swapon`: enable/list swap devices
- [x] `swapoff`: disable swap devices
- [x] `sync`: flush writes
- [x] `chroot`: run a shell/command with a different root directory
- [x] `snapper`: filesystem snapshot management

## Networking / connectivity
- [x] `ip`: addresses, routes, links, and neighbours
- [x] `ss`: sockets, listening ports, and connections
- [x] `ping`: ICMP reachability
- [x] `traceroute`: trace packet path
- [x] `tracepath`: trace path without needing root
- [x] `nslookup`: older DNS lookup
- [x] `host`: simple DNS lookup
- [x] `dig`: DNS lookup and debugging
- [ ] `wget` handles simple downloads

## Network probes / debugging
- [x] `nc`: basic TCP//UDP testing
- [x] `socat`: bidirectional socket/data plumbing
- [ ] `openssl s_client`: TLS endpoint debugging
- [x] `whois`: domain/IP regstry lookup
- [ ] `rdap`: query RDAP registration data for domains and IPs
- [x] `iperf3`: network throughput measurement
- [x] `speedtest`: network speed test CLI
- [x] `tcpdump`: packet capture
- [ ] `tshark`: CLI Wireshark packet analysis
- [x] `nmap`: host/port discovery
- [x] `mtr`: ongoing path quality
- [x] `nethogs`: per-process bandwidth usage
- [ ] `ipcalc`: subnet calculator
- [ ] `testssl.sh`: practical TLS endpoint audit
- [ ] `mitmproxy`: interactive HTTP(S) proxy for inspecting and modifying traffic ([GitHub](https://github.com/mitmproxy/mitmproxy))
- [ ] `mitmdump`: scriptable HTTP(S) proxy capture/debugging from mitmproxy

## Firewall / packet filtering
- [x] `firewall-cmd`: firewalld CLI
- [x] `ufw` is a simple firewall frontend common on Ubuntu

## File transfer / sync fundamentals
- [ ] `rsync`: serious file copy/sync
- [ ] `sshfs` mounts remote directories over SSH

## User management
- [x] `useradd`: create user
- [x] `userdel`: delete user
- [x] `usermod`: modify user
- [x] `groupadd`: create group
- [x] `groupdel`: delete group
- [x] `groupmod`: modify group
- [x] `users`: list currently logged-in users
- [x] `passwd`: change password
- [x] `chsh`: change a user's login shell
- [x] `su`: switch user
- [x] `sudo`: execute as root
- [x] `visudo`: edit sudoers safely
- [x] `sudoedit`: edit root-owned files safely through sudo
- [x] `vipw`: safely edit `/etc/passwd` and related account files
- [x] `vigr`: safely edit `/etc/group` and related group files
- [ ] `pinky` provides lightweight `finger`-style user information
- [ ] `adduser` is a friendlier user-creation wrapper on some systems

## Cron basics
- [x] `crontab`: cron job management

## Package management
- [ ] `rpm`: low-level rpm operations
- [ ] `alternatives`: manage default implementations on Fedora/RHEL
- [ ] `update-alternatives`: manage default implementations for commands
- [ ] `apt`: Debian/Ubuntu package manager
- [ ] `apt-cache`: query Debian/Ubuntu package metadata
- [ ] `dpkg`: low-level Debian package operations

## SSH
- [x] `ssh`: remote shell
- [x] `scp`: remote copy
- [x] `sftp`: remote file transfer
- [x] `ssh-keygen`: key generation
- [x] `ssh-copy-id`: deploy public key
- [x] `ssh-agent`: key agent
- [x] `ssh-add`: add key to agent
- [x] `ssh-keyscan`: grab host keys
- [x] `sshd`: SSH daemon
- [x] `sshpass`: non-interactive SSH password (use keys instead)
- [ ] `autossh` keeps SSH tunnels alive
- [ ] `ssh-audit` audits SSH server/client crypto configuration
- [ ] `xxh` brings your shell environment over SSH without installing dotfiles remotely

## Concepts
- [ ] Networking understanding, HTTP, TCP, SSL and so on.
- [ ] login/session chain: `systemd` -> `getty` -> `login` -> shell/session
- [ ] boot/initramfs/rescue chain: kernel -> initramfs -> `systemd` -> units
- [ ] systemd unit lifecycle
- [ ] journalctl query model
- [ ] filesystem quotas: user/group/project quotas, soft vs hard limits, grace periods
- [ ] DNS lookup path: hosts/NSS/resolved/DNS
- [ ] process accounting: recording executed commands and resource usage for after-the-fact audit/debugging (`acct`, `lastcomm`, `sa`)
- [ ] mount source vs mount target
- [ ] block device vs filesystem vs mountpoint

## Important config locations
- [x] `/etc/passwd`, `/etc/group`, `/etc/shadow`
- [x] `/etc/sudoers`, `/etc/sudoers.d/`
- [x] `/etc/fstab`
- [x] `/etc/hosts`
- [ ] `/etc/resolv.conf`
- [x] `/etc/ssh/sshd_config`
- [x] `/etc/systemd/system/`
- [x] `/usr/lib/systemd/system/`
- [x] `/var/log/`
- [x] `/proc/`
- [x] `/sys/`

## Shell scripting quality
- [ ] `bats`: Bash Automated Testing System
- [ ] `envsubst`: substitute env vars in templates — handy for deploy scripts
- [ ] `dotenvx`: manage/load `.env` files with encryption support
- [ ] `dotenv-linter`: catch mistakes in `.env` files
- [x] `flock`: prevent overlapping cron/systemd jobs with a lockfile
- [ ] `parallel`: GNU parallel — run jobs in parallel properly

## Repo hygiene / CI / linting
- [ ] `trufflehog`: scan Git history and files for secrets; use as a pre-commit hook
- [ ] `gitleaks`: scan repos for committed secrets; use as a pre-commit hook
- [ ] `yamllint`: catch YAML syntax/structure/style issues

## Ansible
- [ ] `ansible`: ad-hoc automation
- [ ] `ansible-inventory`: inspect inventory
- [ ] `ansible-vault`: encrypted secrets
- [ ] `ansible-galaxy`: roles/collections
- [ ] `ansible-lint`: lint playbooks
- [ ] `ansible-doc`: inspect Ansible module/plugin docs locally
- [ ] `ansible-config`: inspect effective Ansible configuration

## Data wrangling
- [ ] `jc` converts common command output to JSON for piping into `jq`
- [ ] `jo` builds JSON objects from shell scripts without quoting hell
- [ ] `gron` flattens JSON into greppable assignments
- [ ] `jd` provides JSON diffs
No
- [ ] `jless` is an interactive JSON viewer
- [ ] `jqp` is a TUI playground for `jq` filters

## Infrastructure debugging
- [ ] `iostat`: CPU and disk I/O trends (sysstat)
- [ ] `pidstat`: per-process CPU, memory, and I/O (sysstat)
- [ ] `lsof`: what has this file/port/socket open
- [ ] `fuser`: identify processes using a file, socket, or filesystem
- [ ] `strace`: (via stap/dtrace) — syscall tracing, find why things hang
- [ ] `ltrace`: trace dynamic library calls, useful beside `strace`
- [ ] `iotop`: per-process I/O usage
- [ ] `dmesg`: kernel ring buffer — hardware events, driver issues
- [ ] `perf`: Linux performance profiling and low-level CPU/system analysis
- [ ] `dd`: block copy (careful with this one)

## SELinux
Rocky Linux means you deal with this.
- [ ] `getenforce`: check SELinux mode
- [ ] `sestatus`: SELinux status
- [ ] `setenforce`: set SELinux mode
- [ ] `restorecon`: fix file contexts
- [ ] `audit2why`: explain SELinux denials

## Security / audit
- [ ] `lynis`: Linux security audit/checklist tool
- [ ] `auditd`: Linux audit daemon

## Containers
Fedora-native defaults apply.
- [ ] `skopeo` inspects and copies container images without pulling
- [ ] `cosign` signs and verifies container images/artifacts
- [ ] `trivy` scans images, filesystems, and IaC for security issues
- **NOTE:** There are more container tools in [[command-triage-additions]]
- [ ] `toolbox` provides Fedora containerised development environments
- [ ] `distrobox` provides a broader Linux desktop/dev container workflow than `toolbox`
- [ ] `lazydocker` is a TUI for local Docker/Compose stacks

## Certificate/TLS
Relevant to your Caddy and internal PKI work.
- [ ] `openssl`: cert inspection, CSR generation, TLS debugging
- [ ] `trust`: manage system trust store
- [ ] `update-ca-trust`: refresh CA bundle

## Secrets / credentials
- [ ] `gpg`: encryption/signing
- [ ] `pass`: Unix password manager
- [ ] `age`: modern file encryption
- [ ] `sops`: encrypted config/secrets, often with age/KMS

## Backup/recovery
- [ ] `restic`: deduplicated encrypted backups
- [ ] `borg`: deduplicated encrypted backups, good alternative to `restic`

## Process/resource tuning
- [ ] `sysctl`: kernel parameter tuning
- [ ] `ionice`: I/O priority
- [ ] `taskset`: CPU affinity
- [ ] `prlimit`: per-process limits

## Logs
- [ ] `logrotate`: rotat kie logs
- [ ] `logger`: write message to syslog/journal
- [ ] `lnav`: interactive log viewer for mixed log files and timestamps

## Language/runtime tooling
- [ ] `perl`: regular expressions and older scripting glue

## Build / compile basics
- [ ] `make`: build automation
- [ ] `watch` repeats a command and displays its changing output
- [ ] `watchexec` reruns commands when files change
- [ ] `entr` reruns commands when listed files change

## Shell / legacy scripting
- [ ] `expr`: legacy arithmetic/string evaluator you still see in older shell scripts

## CLI calculators
- [ ] `dc` is a reverse-polish stack calculator; mostly worth recognising rather than prioritising

## Occasional scheduling
- [x] `anacron`: run missed cron jobs
- [x] `at`: one-shot scheduled command
- [x] `atq`: list at queue
- [x] `atrm`: remove at job
- [x] `batch`: run when load is low

## Mail/server notifications
- [ ] `mailx`: send/read simple mail
- [ ] `swaks`: scriptable SMTP test client for mail delivery debugging
- [ ] `sendmail`: sendmail-compatible interface
- [ ] `postqueue`: inspect Postfix queue
- [ ] `postfix`: Postfix control

## Spell checking / writing
- [ ] `vale`: prose/style linter for Markdown and documentation
- [ ] `look`: prefix lookup in sorted word lists/dictionaries; handy, but much lower priority than actual spell checkers

## Additional file transfer / sync
- [ ] `rclone`: cloud storage sync (S3, etc.)
- [ ] `syncthing`: p2p file sync
- [ ] `croc` provides simple encrypted file transfer between machines

## Environment / dotfiles
- [ ] `chezmoi`: dotfiles manager for multi-machine setups

## Pipeline helpers
- [ ] `pv`: monitor progress through a pipe / long data stream
- [ ] `sponge`: soak stdin before writing a file, useful in pipelines that update files in place

## VM / local lab
- [ ] `vagrant`: VM provisioning (your ansible testing)

## Archiving/compression
- [ ] `pigz`: parallel gzip for faster compression/decompression
- [ ] `unar`: extract many archive formats with fewer flags to remember

## Terminal mail
- [ ] `mutt`: text-based mail client when staying in the terminal is faster than context-switching to a browser
- [ ] `mail`: minimal text-based mail client for simple send/read flows
- [ ] `mailq`: inspect the local outgoing mail queue

## Text/doc conversion
- [x] `pandoc`: universal doc converter — markdown to PDF, docx, etc.
- [ ] `pdfgrep`: grep through PDF text
- [ ] `pdftotext`: extract text from PDFs
- [ ] `ocrmypdf`: OCR + PDF optimization — useful for law firm doc scanning
- [ ] `dos2unix`: fix Windows line endings

## Code / repo utilities
- [ ] `cloc`: count lines of code

## Printing / scanning
- [ ] `lp`: submit files to print

## Desktop / media helpers
- [ ] `chafa`: render images in the terminal; handy for quickly inspecting screenshots without leaving the shell
- [ ] `playerctl`: control media players from the shell
- [ ] `brightnessctl`: control laptop/display brightness from the shell
- [ ] `yt-dlp`: video downloader

## AI / local models
- [ ] `herdr`: terminal workspace for running and monitoring multiple coding agents ([GitHub](https://github.com/ogulcancelik/herdr))
- [ ] `bd` / Beads: distributed graph issue tracker and persistent structured memory for AI agents ([GitHub](https://github.com/gastownhall/beads))
- [ ] `aider`: AI pair-programming CLI for editing code in local git repos ([site](https://aider.chat/))
- [ ] `opencode`: terminal-based AI coding agent
- [ ] `llm`: CLI and Python library for running prompts, managing models, and logging responses ([GitHub](https://github.com/simonw/llm))
- [ ] `sgpt` / `shell_gpt`: terminal AI assistant for shell commands, code, and chat ([GitHub](https://github.com/ther1d/shell_gpt))
- [ ] `ollama`: local LLM inference (your GPU passthrough setup)

## Personal workflow
- [ ] `jrnl`: simple personal diary app
- [ ] `tuxedo`: keyboard-driven TUI/CLI for `todo.txt` task lists ([GitHub](https://github.com/webstonehq/tuxedo))

---

## X11/Wayland tools
- [ ] `grim`: Wayland screenshot capture
- [ ] `slurp`: select a Wayland screen region, often used with `grim`
- [ ] `swappy`: annotate/edit screenshots from Wayland capture workflows
- [ ] `wl-screenrec`: Wayland screen recording
- [ ] `wl-paste`: Wayland clipboard paste

## Related
- [ ] Review [[Firefox]]
