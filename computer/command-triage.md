**https**://github.com/facebook/sapling

NOTE: We also need to do [[zsh]] and [[Firefox]] too.

## TIER 1: Core daily drivers (you almost certainly know these)

**Git**
- [ ] `git`: version control
  - [ ] Standalone developer workflow
    - [ ] `git config`: inspect/set identity, defaults, aliases, and tool integration
    - [x] `git init`: create a new repository
    - [x] `git log`: see what happened
    - [x] `git show`: inspect one commit, tag, or object
    - [ ] `git reflog`: recover where branches/HEAD used to point
    - [x] `git switch`
    - [x] `git branch`: switch and manage branches
    - [x] `git add`: manage the index/staging area
    - [x] `git diff`
    - [x] `git status`: see what you are in the middle of doing
    - [ ] `git commit`: advance the current branch
		- Got up to --fixup (learn rebase first)
    - [x] `git restore`: undo changes
    - [x] `git reset`: move HEAD/index and undo staged work
    - [x] `git clean`: remove untracked files/directories
    - [x] `git rm`, `git mv`: remove/rename tracked files
    - [x] `git stash`: park dirty work temporarily to 
    - [x] `git merge`: merge between local branches
	    - [ ] Come back to --cleanup=
    - [ ] `git rebase`: maintain topic  branches
    - [x] `git cherry-pick`: apply syelected commits onto the current branch
    - [x] `git bisect`: find the commit that introduced a regression
    - [ ] `git blame`: trace which commit last changed lines
    - [x] `git grep`: search tracked files quickly
    - [x] `git tag`: mark a known point
  - [ ] Individual developer participant workflow
    - [x] `git clone`: prime a local repository from upstream
    - [x] `git remote`: inspect and manage upstream remotes
    - [x] `git pull`, `git fetch`: keep up to date with upstream
    - [ ] `git push`: publish to a shared repository
    - [ ] `git submodule`: manage nested external repositories when a project uses them
  - [ ] Occasional but important Git workflows
    - [ ] `git mergetool`, `git difftool`: use external tools for conflicts and diffs
    - [ ] `git ls-files`: show files tracked by Git
    - [ ] `git rev-parse`: scripting helper for repo roots, refs, and object names
    - [ ] `git describe`: derive human-readable version strings from tags and commits
    - [ ] `git filter-repo`: rewrite history for cleanup or secret removal; learn carefully when needed
    - [ ] `git archive`: export a clean tar/zip snapshot of tracked files at a commit
    - [ ] `git fsck`: check repository object integrity when diagnosing corruption
    - [ ] `git format-patch`, `git am`: email/patch-based contribution workflow
- [x] `git worktree`
- [ ] `git-absorb`: automatically create `fixup!` commits by matching staged changes to earlier commits
- [ ] `gitrevisions`: Git revision/range syntax
- [ ] `gitk`: GUI log
- [ ] `gh`: GitHub CLI
- [ ] `gh-dash`: terminal dashboard for GitHub pull requests and issues
- [ ] `ghq`: clone/manage many repos under one directory
- [ ] `hunk`: review-first terminal diff viewer for agent-authored changesets
- [ ] Worktrunk and similar worktree managers
- [ ] https://blog.jcoglan.com/2017/05/08/merging-with-diff3/

**Modern CLI replacements — big quality-of-life wins**
- [x] `fd`: fast, intuitive find replacement. Pairs with fzf
- [ ] `eza`: modern `ls` replacement
- [x] `rg`: ripgrep — fast recursive grep with sane defaults
- [ ] `ast-grep`: search and rewrite code by syntax structure rather than plain text
- [ ] `rga` / `ripgrep-all`: search PDFs, Office docs, archives, and other rich files with ripgrep-like ergonomics
- [ ] `bat`: cat with syntax highlighting and git integration
- [ ] `yazi`: file browser tui
- [ ] `fzf`: fuzzy finder — transforms how you navigate
- [ ] `fzf-tab`: zsh plugin for fzf-powered tab completion
- [ ] `fzf-tmux`: fzf inside tmux panes
- [x] `atuin`: much better shell history/search
- [ ] `zoxide`: smarter cd with frecency tracking
- [ ] `delta`: beautiful git diffs, pairs with lazygit
- [ ] `difft`: Difftastic syntax-aware structural diff tool ([GitHub](https://github.com/Wilfred/difftastic))
- [ ] `hyperfine`: benchmark commands properly
- [ ] `gum`: build polished interactive shell script prompts and menus
- [ ] `btop`: gorgeous process/resource monitor
- [ ] `ncdu`: interactive disk usage explorer — find what's eating space
- [ ] `lazygit`: TUI git client you already use
-  pull requests?
- [ ] `tree`: directory tree view

**Terraform / image build**
- [ ] `terraform`: core workflow (`fmt`, `validate`, `plan`, `apply`, `output`, `state`, `console`, `import`)
- [ ] `tflint`: lint Terraform and catch provider-specific mistakes
- [ ] `terraform-docs`: generate docs for Terraform modules
- [ ] `terraform-ls`: Terraform language server
- [ ] `tfsec`: Terraform static security scanning
- [ ] `infracost`: estimate Terraform/OpenTofu cloud costs

**AWS**
- [ ] `aws`: AWS CLI
- [ ] `aws-vault`: safer AWS credential handling
- [ ] `granted`: switch AWS accounts, profiles, and assumed roles
- [ ] `aws sts get-caller-identity`: fastest identity/account sanity check
- [ ] `aws sso login`: authenticate with AWS IAM Identity Center / SSO
- [ ] `aws configure sso`: initial SSO profile setup

**Docs / discovery**
- [x] `man`: primary system manuals
- [x] `apropos`: find commands by keyword
- [x] `whatis`: one-line command descriptions
- [x] `whereis`
- [x] `info`: GNU manuals when `man` is thin
- [ ] `navi`: interactive, searchable command cheatsheets

**Shell basics**
- [x] `bash`: your shell            
- [ ] `zsh`: alternative shell (learn line editing here)
- [x] `cd`: change directory
- [x] `pwd`: print working directory
- [x] `ls`: list files
- [x] `cp`: copy 
- [x] `mv`: move/rename
- [x] `rm`: remove
- [x] `rmdir`: remove empty dirs
- [x] `mkdir`: make dirs
- [x] `ln`: links (hard + symlinks)
- [x] `touch`: create/update timestamps
- [x] `cat`: concatenate/display files
- [x] `less`: pager
- [x] `head`: first N lines
- [x] `tail`: last N lines (tail -f for log following)
- [x] `echo`: print text
- [x] `printf`: formatted print
- [x] `read`: read input in scripts
- [x] `time`: measure how long a command takes
- [x] `test`: conditional evaluation ([ ])
- [x] `true`: exit 0
- [x] `false`: exit 1
- [x] `yes`: repeat string forever
- [x] `sleep`: delay for a fixed duration
- [x] `seq`: generate numeric sequences for loops, filenames, and quick test data

**Shell language / builtins**
- [x] `type`: show whether something is a shell builtin, alias, function, or binary
- [x] `which`: locate a command in `PATH`; prefer `type` for shell-aware lookup
- [x] `help`: shell builtin docs
- [x] `command`: run command bypassing shell functions/aliases
- [x] `builtin`: run shell builtin explicitly
- [x] `alias`: define/list aliases
- [x] `unalias`: remove aliases
- [x] `export`: put variables into environment
- [x] `unset`: remove variable/function
- [x] `set`: shell options + positional parameters
- [x] `shopt`: Bash-specific shell options
- [x] `source`: run file in current shell
- [x] `.`: POSIX source
- [x] `pushd`: push the current directory onto the stack and switch directories
- [x] `popd`: pop a directory off the stack and switch back to it
- [x] `dirs`: show or manipulate the shell directory stack
- [x] `exec`: replace current shell/process
- [x] `trap`: handle signals/cleanup in scripts
- [x] `return`: return from function/sourced script
- [x] `exit`: exit shell/script
- [x] `shift`: shift positional parameters
- [ ] `getopts`: parse shell script flags
- [x] `ulimit`: shell resource limits
- [x] `history`: shell history
- [x] `fc`: edit/re-run previous commands
- [x] `bindkey`: zsh keybindings
- [x] `bind`: bash/readline keybindings
- [x] `declare`: set shell variables and attributes

**Text processing**
- [x] `grep`: pattern search
- [x] `sed`: stream editor [Read this](https://www.grymoire.com/Unix/Sed.html)
- [x] `awk`: pattern/action language
	- [ ] https://catonmat.net/awk-book
- [x] `sort`: sort lines
- [x] `uniq`: deduplicate adjacent lines
- [x] `wc`: word/line/byte count
- [x] `cut`: extract fields
- [x] `tr`: translate/delete characters
- [x] `tee`: split stdout to file + pipe
- [x] `stdbuf`: adjust stdio buffering in pipelines
- [x] `xargs`: build commands from stdin
- [x] `diff`: compare files
- [ ] `diff3`: three-way file comparison
- [x] `sdiff`: side-by-side diff
- [x] `patch`: apply diffs
- [ ] `comm`: compare sorted files line by line
	- [ ] We need -1,-2,3 as cards.
- [x] `paste`: merge lines side by side
- [x] `join`: join sorted text files on a shared field
- [x] `column`: format into columns
- [x] `numfmt`: convert numbers to/from human-readable units
- [x] `fold`: wrap lines
- [x] `fmt`: simple text formatter
- [x] `expand`: tabs to spaces
- [x] `unexpand`: spaces to tabs
- [x] `cmp`
- [x] `shuf`
- [x] `rev`: reverse lines
- [x] `tac`: reverse file (cat backwards)
- [x] `nl`: number lines

**File operations**
- [x] `find`: search filesystem
- [x] `locate`: fast filename lookup via a prebuilt database
- [x] `updatedb`: refresh the `locate` database
- [x] `chmod`: change permissions
- [x] `chown`: change ownership
- [x] `chgrp`: change group
- [ ] `rename`: batch rename files
- [ ] `trash-cli`: safer interactive delete workflow than raw `rm`
- [x] `stat`: file metadata
- [x] `file`: detect file type
- [x] `realpath`: resolve symlinks
- [x] `readlink`: read symlink target
- [x] `gio`: GLib/GVfs file and metadata operations
- [x] `basename`: strip directory from path
- [x] `dirname`: strip filename from path
- [x] `mktemp`: create temp file/dir
- [x] `mkfifo`: create named pipes
- [x] `split`: split a file into smaller chunks
- [x] `truncate`: shrink or extend a file to a specific size
- [x] `install`: copy with permissions
- [x] `link`: create hard link
- [x] `unlink`: remove single file
- [x] `lsattr`: list Linux extended file attributes

**Permissions / identity / access**
- [x] `umask`: default permissions for newly created files
- [x] `getfacl`: view POSIX ACLs
- [x] `setfacl`: set POSIX ACLs
- [x] `namei`: follow path components and permissions
- [x] `getcap`: view file capabilities
- [x] `setcap`: set file capabilities
- [x] `runuser`: run command as another user, often from root scripts

**Archiving/compression**
- [x] `tar`: tape archive (tar czf, tar xzf)
- [x] `gzip`: gzip compression
- [ ] `pigz`: parallel gzip for faster compression/decompression
- [x] `gunzip`: decompress gzip
- [x] `zcat`: cat compressed files
- [x] `unzip`: extract zip archives
- [ ] `unar`: extract many archive formats with fewer flags to remember

**Checksums / encoding / binary inspection**
- [x] `sha256sum`: verify file hash
- [x] `sha512sum`: verify file hash
- [ ] `rhash`: compute many hash formats
- [x] `base64`: encode/decode base64
- [x] `xxd`: hex dump / reverse hex dump
- [x] `hexdump`: inspect binary data
- [x] `od`: byte/word dumps with precise numeric formatting
- [x] `strings`: extract printable strings from binaries

**Process management**
- [x] `ps`: process list
- [x] `pstree`: process tree view - parent/child relationships at a glance
- [x] `kill`: send signal
- [x] `killall`: kill by name
- [x] `pgrep`: find process by pattern
- [x] `pkill`: kill by pattern
- [x] `top`: process monitor
- [x] `htop`: better process monitor
- [x] `bg`: background job
- [x] `fg`: foreground job
- [x] `jobs`: list shell jobs
- [x] `nohup`: survive logout
- [x] `wait`: wait for background jobs
- [x] `nice`: set priority
- [x] `renice`: change priority
- [x] `timeout`: run with time limit

**Terminal / TTY**
- [x] `stty`: terminal line settings
- [x] `tty`: print current terminal device
- [x] `reset`: reset broken terminal
- [x] `clear`: clear terminal screen
- [x] `script`: record terminal session
- [ ] `asciinema`: record terminal sessions
- [ ] `agg`: turn asciinema recordings into GIF/video
- [ ] `vhs`: script terminal demos and recordings
- [ ] `tmux`: terminal multiplexer

**System info**
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

**Login/session/account state**
- [x] `last`: login history
- [x] `lastlog`: last login per user
- [x] `w`: logged-in users + what they are doing
- [x] `logname`: original login name
- [x] `newgrp`: switch current group

**Disk/filesystem**
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

**Networking / connectivity**
- [x] `ip`: addresses, routes, links, and neighbours
- [x] `ss`: sockets, listening ports, and connections
- [x] `ping`: ICMP reachability
- [x] `traceroute`: trace packet path
- [x] `tracepath`: trace path without needing root
- [x] `nslookup`: older DNS lookup
- [x] `host`: simple DNS lookup
- [x] `dig`: DNS lookup and debugging
- [x] `curl`: HTTP/API checks
- [ ] `wget`: simple downloads

**Network probes / debugging**
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

**Firewall / packet filtering**
- [x] `firewall-cmd`: firewalld CLI
- [ ] `ufw`: simple firewall frontend common on Ubuntu

**File transfer / sync**
- [ ] `rsync`: serious file copy/sync
- [ ] `sshfs`: mount remote directories over SSH

**User management**
- [x] `useradd`: create user
- [x] `userdel`: delete user
- [x] `usermod`: modify user
- [x] `groupadd`: create group
- [x] `groupdel`: delete group
- [x] `groupmod`: modify group
- [x] `users`: list currently logged-in users
- [ ] `pinky`: lightweight `finger`-style user info
- [ ] `adduser`: friendlier user creation wrapper on some systems
- [x] `passwd`: change password
- [x] `chsh`: change a user's login shell
- [x] `su`: switch user
- [x] `sudo`: execute as root
- [x] `visudo`: edit sudoers safely
- [x] `sudoedit`: edit root-owned files safely through sudo
- [x] `vipw`: safely edit `/etc/passwd` and related account files
- [x] `vigr`: safely edit `/etc/group` and related group files

**Systemd / logs**
- [ ] `systemctl`: service/unit management (`status`, `list-units`, `cat`, `edit`, `daemon-reload`)
- [ ] `journalctl`: log viewer (`-u`, `-b`, `-f`)
- [ ] `oomctl`: inspect systemd-oomd state
- [ ] `shutdown`: schedule or trigger shutdown/reboot on modern systemd systems
- [ ] `reboot`: trigger an immediate reboot
- [ ] `poweroff`: power the system down immediately
- [ ] `halt`: halt the machine; usually prefer `systemctl poweroff`
- [ ] `rtcwake`: suspend/hibernate until a scheduled wake time
- [x] `timedatectl`: time/timezone/NTP state

**Cron / scheduling**
- [x] `crontab`: cron job management

**Package management**
- [ ] `dnf`: Fedora/RHEL package manager
- [ ] `rpm`: low-level rpm operations
- [ ] `alternatives`: manage default implementations on Fedora/RHEL
- [ ] `update-alternatives`: manage default implementations for commands
- [ ] `brew`: Homebrew package manager, common on macOS and useful via Linuxbrew
- [ ] `apt`: Debian/Ubuntu package manager
- [ ] `apt-cache`: query Debian/Ubuntu package metadata
- [ ] `dpkg`: low-level Debian package operations

**SSH**
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
- [ ] `autossh`: keep SSH tunnels alive
- [ ] `ssh-audit`: audit SSH server/client crypto configuration
- [ ] `xxh`: bring your shell environment over SSH without installing dotfiles remotely

**Editors**
- [x] `nvim`: your editor
- [x] `vim`: fallback
- [x] `vi`: minimal vim
- [x] `view`: read-only vim
- [x] `ctags`: generate source navigation tags

**Concepts to learn as concepts, not binaries**
- [ ] shell expansion order
- [x] quoting rules
- [ ] PATH lookuk
- [ ] Networking understanding, HTTP, TCP, SSL and so on.
- [ ] HTTP request/response model: methods, headers, status codes, bodies, redirects, caching, cookies, and auth basics
- [ ] fast doc lookup: official docs first, then `site:` search by tool/vendor
- [ ] Terraform lookup model: language docs vs provider docs vs registry module docs
- [ ] browser keyword search shortcuts / DevDocs for fast web-doc lookup
- [ ] login/session chain: `systemd` -> `getty` -> `login` -> shell/session
- [ ] boot/initramfs/rescue chain: kernel -> initramfs -> `systemd` -> units
- [ ] cgroups vs namespaces vs systemd units
- [ ] systemd unit lifecycle
- [ ] journalctl query model
- [ ] file ownership vs permissions vs ACLs
- [ ] filesystem quotas: user/group/project quotas, soft vs hard limits, grace periods
- [ ] DNS lookup path: hosts/NSS/resolved/DNS
- [ ] process/session/job distinction
- [ ] process accounting: recording executed commands and resource usage for after-the-fact audit/debugging (`acct`, `lastcomm`, `sa`)
- [ ] mount source vs mount target
- [ ] block device vs filesystem vs mountpoint
- [ ] package ownership: which package installed this file?
- [ ] OIDC and OAuth flow


**Important config locations**
- [x] `/etc/passwd`, `/etc/group`, `/etc/shadow`
- [x] `/etc/sudoers`, `/etc/sudoers.d/`
- [x] `/etc/fstab`
- [x] `/etc/hosts`
- [ ] `/etc/resolv.conf`
- [x] `/etc/ssh/sshd_config`
- [x] `/etc/systemd/system/`
- [x] `/usr/lib/systemd/system/`
- [x] `/etc/profile`, `~/.profile`, `~/.bashrc`, `~/.zshrc`
- [x] `/var/log/`
- [x] `/proc/`
- [x] `/sys/`

## TIER 2: High-value tools to invest in learning

**Current focus: AWS + PostgreSQL/MySQL**

**Shell scripting quality**
- [x] `shellcheck`: static analysis for shell scripts — catches real bugs
- [x] `shfmt`: shell script formatter (use with conform.nvim)
	- Add this to the pre commit.
- [ ] `bats`: Bash Automated Testing System
- [ ] `envsubst`: substitute env vars in templates — handy for deploy scripts
- [ ] `dotenvx`: manage/load `.env` files with encryption support
- [ ] `dotenv-linter`: catch mistakes in `.env` files
- [x] `flock`: prevent overlapping cron/systemd jobs with a lockfile
- [ ] `parallel`: GNU parallel — run jobs in parallel properly

**Repo hygiene / CI / linting**
- [ ] `pre-commit`: run the same local hooks as CI
  - [ ] `trufflehog`: scan Git history and files for secrets; use as a pre-commit hook
  - [ ] `gitleaks`: scan repos for committed secrets; use as a pre-commit hook
- [ ] `act`: run GitHub Actions locallyz
- [ ] `actionlint`: lint GitHub Actions workflows
- [ ] `zizmor`: audit GitHub Actions workflows for security problems
- [ ] `yamllint`: catch YAML syntax/structure/style issues

**Ansible**
- [ ] `ansible`: ad-hoc automation
- [ ] `ansible-playbook`: run playbooks
- [ ] `ansible-inventory`: inspect inventory
- [ ] `ansible-vault`: encrypted secrets
- [ ] `ansible-galaxy`: roles/collections
- [ ] `ansible-lint`: lint playbooks
- [ ] `ansible-doc`: inspect Ansible module/plugin docs locally
- [ ] `ansible-config`: inspect effective Ansible configuration

**Data wrangling**
- [ ] `jq`: JSON query/transform — essential for API work, terraform state
- [ ] `yq`: YAML equivalent of jq — critical for ansible debugging
- [ ] `jc`: convert common command output to JSON for piping into `jq`
- [ ] `jo`: build JSON objects from shell scripts without quoting hell
- [ ] `gron`: flatten JSON into greppable assignments
- [ ] `jless`: interactive JSON viewer
- [ ] `jqp`: TUI playground for `jq` filters
- [ ] `jd`: JSON diff

**Infrastructure debugging**
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

**SELinux (Rocky Linux means you deal with this)**
- [ ] `getenforce`: check SELinux mode
- [ ] `sestatus`: SELinux status
- [ ] `setenforce`: set SELinux mode
- [ ] `restorecon`: fix file contexts
- [ ] `audit2why`: explain SELinux denials

**Security / audit**
- [ ] `lynis`: Linux security audit/checklist tool
- [ ] `auditd`: Linux audit daemon

**Containers (Fedora native)**
- [ ] `podman`: rootless containers — docker-compatible
- [ ] `docker`: still the lingua franca even if you prefer podman
- [ ] `docker compose`: local multi-container stacks
- [ ] `podman compose`: compose-style podman workflow
- [ ] `skopeo`: inspect/copy container images without pulling
- [ ] `cosign`: sign and verify container images/artifacts
- [ ] `trivy`: image/filesystem/IaC security scanning
- [ ] `toolbox`: Fedora containerised development environments
- [ ] `distrobox`: Linux desktop/dev container workflow, broader than `toolbox`
- [ ] `lazydocker`: TUI for local Docker/Compose stacks
- **NOTE:** There are more container tools in [[command-triage-additions]]

**Certificate/TLS (relevant to your Caddy + internal PKI work)**
- [ ] `openssl`: cert inspection, CSR generation, TLS debugging
- [ ] `trust`: manage system trust store
- [ ] `update-ca-trust`: refresh CA bundle

**Secrets / credentials**
- [ ] `gpg`: encryption/signing
- [ ] `secret-tool`: query/store secrets via libsecret
- [ ] `pass`: Unix password manager
- [ ] `bw`: Bitwarden CLI
- [ ] `age`: modern file encryption
- [ ] `sops`: encrypted config/secrets, often with age/KMS

**Databases / cache**
- [ ] `psql`: PostgreSQL shell for inspection and admin
- [ ] `pgcli`: enhanced PostgreSQL shell with completion and syntax highlighting
- [ ] `pg_isready`: fast PostgreSQL readiness/connectivity check
- [ ] `pg_dump`: logical backup of a PostgreSQL database
- [ ] `pg_restore`: restore `pg_dump` custom/directory backups
- [ ] `pg_dumpall`: dump all PostgreSQL databases plus global objects like roles
- [ ] `pg_basebackup`: physical PostgreSQL backup / replication base backup
- [ ] `createdb`: create a PostgreSQL database from the CLI
- [ ] `createuser`: create PostgreSQL roles/users from the CLI
- [ ] `vacuumdb`: run vacuum/analyze/maintenance without opening `psql`
- [ ] `reindexdb`: rebuild indexes when debugging corruption or bloat issues
- [ ] `mysql`: MySQL/MariaDB shell for inspection and admin
- [ ] `mycli`: enhanced MySQL/MariaDB shell with completion and syntax highlighting
- [ ] `mysqldump`: logical backup of a MySQL/MariaDB database
- [ ] `mysqladmin`: quick admin/status operations without opening the full shell
- [ ] `redis-cli`: Redis inspection and debugging
- [ ] `sqlite3`: inspect and query SQLite databases

**Backup/recovery**
- [ ] `restic`: deduplicated encrypted backups
- [ ] `borg`: deduplicated encrypted backups, good alternative to `restic`

**Process/resource tuning**
- [ ] `sysctl`: kernel parameter tuning
- [ ] `ionice`: I/O priority
- [ ] `taskset`: CPU affinity
- [ ] `prlimit`: per-process limits

**Logs**
- [ ] `logrotate`: rotat kie logs
- [ ] `logger`: write message to syslog/journal
- [ ] `lnav`: interactive log viewer for mixed log files and timestamps

**Terminal mail**
- [ ] `mutt`: text-based mail client when staying in the terminal is faster than context-switching to a browser
- [ ] `mail`: minimal text-based mail client for simple send/read flows
- [ ] `mailq`: inspect the local outgoing mail queue

**Language/runtime tooling**
- [ ] `python3`: Python interpreter
- [ ] `pip`: Python package installer
- [ ] `pipx`: install Python CLI apps cleanly
- [ ] `venv`: Python virtual environments
- [ ] `node`: JavaScript runtime
- [ ] `npm`: Node package manager
- [ ] `perl`: regular expressions and older scripting glue

**Build / compile basics**
- [ ] `make`: build automation
- [ ] `watch`: repeat command and watch output
- [ ] `watchexec`: rerun commands when files change
- [ ] `entr`: rerun commands when listed files change
- [ ] `just`: command runner (you already use this)

---

## TIER 3: Good to know exist, learn when needed

**Shell / legacy scripting**
- [ ] `expr`: legacy arithmetic/string evaluator you still see in older shell scripts

**CLI calculators**
- [ ] `bc`: arbitrary-precision calculator for shell math, unit conversions, and quick ops arithmetic
- [ ] `dc`: reverse-polish stack calculator; mostly worth recognizing rather than prioritizing

**Text/doc conversion**
- [x] `pandoc`: universal doc converter — markdown to PDF, docx, etc.
- [ ] `pdfgrep`: grep through PDF text
- [ ] `pdftotext`: extract text from PDFs
- [ ] `ocrmypdf`: OCR + PDF optimization — useful for law firm doc scanning
- [ ] `dos2unix`: fix Windows line endings

**Spell checking / writing**
- [ ] `aspell`: interactive CLI spell checker for prose, notes, and Markdown
- [ ] `hunspell`: dictionary-based spell checker used by many editors and language packs
- [ ] `codespell`: catch common misspellings in code, docs, and config files
- [ ] `typos`: fast repo-wide spell checker for source, filenames, and CI
- [ ] `vale`: prose/style linter for Markdown and documentation
- [ ] `look`: prefix lookup in sorted word lists/dictionaries; handy, but much lower priority than actual spell checkers

**Cron / scheduling**
- [x] `anacron`: run missed cron jobs
- [x] `at`: one-shot scheduled command
- [x] `atq`: list at queue
- [x] `atrm`: remove at job
- [x] `batch`: run when load is low

**Mail/server notifications**
- [ ] `mailx`: send/read simple mail
- [ ] `swaks`: scriptable SMTP test client for mail delivery debugging
- [ ] `sendmail`: sendmail-compatible interface
- [ ] `postqueue`: inspect Postfix queue
- [ ] `postfix`: Postfix control

**File transfer / sync**
- [ ] `croc`: simple encrypted file transfer between machines
- [ ] `rclone`: cloud storage sync (S3, etc.)
- [ ] `syncthing`: p2p file sync

**Code / repo utilities**
- [ ] `cloc`: count lines of code

**Environment / dotfiles**
- [ ] `stow`: symlink farm manager (your dotfiles)
- [ ] `direnv`: per-directory env vars
- [ ] `chezmoi`: dotfiles manager for multi-machine setups

**Pipeline helpers**
- [ ] `pv`: monitor progress through a pipe / long data stream
- [ ] `sponge`: soak stdin before writing a file, useful in pipelines that update files in place

**Terminal docs / browsing**
- [ ] `w3m`: terminal web browser
- [ ] `glow`: terminal markdown renderer
- [ ] `cheat`: cheat sheets in terminal
- [ ] `tldr`: short, example-first command docs
- [ ] `cht.sh`: curlable cheat sheets / quick example

**Printing / scanning**
- [ ] `lp`: submit files to print

**Desktop / media helpers**
- [ ] `chafa`: render images in the terminal; handy for quickly inspecting screenshots without leaving the shell
- [ ] `playerctl`: control media players from the shell
- [ ] `brightnessctl`: control laptop/display brightness from the shell
- [ ] `xdg-open`: open a file/URL with the desktop default app
- [ ] `yt-dlp`: video downloader

**AI / local models**
- [ ] `pi`: coding agent CLI for AI-assisted code/file edits and terminal workflows
- [ ] `herdr`: terminal workspace for running and monitoring multiple coding agents ([GitHub](https://github.com/ogulcancelik/herdr))
- [ ] `bd` / Beads: distributed graph issue tracker and persistent structured memory for AI agents ([GitHub](https://github.com/gastownhall/beads))
- [ ] `aider`: AI pair-programming CLI for editing code in local git repos ([site](https://aider.chat/))
- [ ] `opencode`: terminal-based AI coding agent
- [ ] `claude code`: Anthropic's agentic coding CLI
- [ ] `llm`: CLI and Python library for running prompts, managing models, and logging responses ([GitHub](https://github.com/simonw/llm))
- [ ] `sgpt` / `shell_gpt`: terminal AI assistant for shell commands, code, and chat ([GitHub](https://github.com/ther1d/shell_gpt))
- [ ] `ollama`: local LLM inference (your GPU passthrough setup)

**VM / local lab**
- [ ] `vagrant`: VM provisioning (your ansible testing)

**Personal workflow**
- [ ] `jrnl`: simple personal diary app
- [ ] `tuxedo`: keyboard-driven TUI/CLI for `todo.txt` task lists ([GitHub](https://github.com/webstonehq/tuxedo))

---

## TIER 4: Niche / special-purpose (ignore until relevant)

**X11/Wayland tools**
- [ ] `grim`: Wayland screenshot capture
- [ ] `slurp`: select a Wayland screen region, often used with `grim`
- [ ] `swappy`: annotate/edit screenshots from Wayland capture workflows
- [ ] `wl-screenrec`: Wayland screen recording
- [ ] `wl-copy`: Wayland clipboard copy
- [ ] `wl-paste`: Wayland clipboard paste

**Flatpak**
- [ ] `flatpak`: Flatpak package manager
