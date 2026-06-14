***#ai-written 
# Command Triage: What to Learn vs Ignore

Everything from your system's PATH, categorised.

NOTE: We also need to do [[zsh]] and [[Firefox]] too.

## TIER 1: Core daily drivers (you almost certainly know these)

**Docs / discovery**
- [x] `man`: primary system manuals
- [x] `apropos`: find commands by keyword
- [x] `whatis`: one-line command descriptions
- [x] `whereis`
- [x] `info`: GNU manuals when `man` is thin

**Shell basics**
- [x] `bash`: your shell            
- [ ] `zsh`: alternative shell (learn lne editing here)
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
- [x] `seq`: generate numeric sequences for loops, filenames, and quick tsed is worth learning to fluency in its core operations. 

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
- [x] `getopts`: parse shell script flags
- [x] `ulimit`: shell resource limits
- [x] `history`: shell history
- [x] `fc`: edit/re-run previous commands
- [ ] `bindkey`: zsh keybindings
- [x] `bind`: bash/readline keybindings
- [x] declare
**Text processing**
- [x] `grep`: pattern search
- [x] `sed`: stream editor [Read this](https://www.grymoire.com/Unix/Sed.html)
- [ ] `awk`: pattern/action language
- [ ] `gawk`: GNU awk
- [x] `sort`: sort lines
- [x] `uniq`: deduplicate adjacent lines
- [x] `wc`: word/line/byte count
- [x] `cut`: extract fields
- [x] `tr`: translate/delete characters
- [x] `tee`: split stdout to file + pipe
- [x] `stdbuf`: adjust stdio buffering in pipelines
- [x] `xargs`: build commands from stdin
- [x] `diff`: compare files
- [x] `sdiff`: side-by-side diff
- [x] `patch`: apply diffs
- [x] `comm`: compare sorted files line by line
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
- [x] `chattr`: change Linux extended file attributes
- [x] `lsattr`: list Linux extended file attributes

**Permissions / identity / access**
- [x] `umask`: default permissions for newly created files
- [x] `getfacl`: view POSIX ACLs
- [x] `setfacl`: set POSIX ACLs
- [x] `namei`: follow path components and permissions
- [x] `capsh`: inspect Linux capabilities
- [x] `getcap`: view file capabilities
- [x] `setcap`: set file capabilities
- [x] `runuser`: run command as another user, often from root scripts

**Archiving/compression**
- [ ] `tar`: tape archive (tar czf, tar xzf)
- [x] `gzip`: gzip compression
- [x] `gunzip`: decompress gzip
- [x] `zcat`: cat compressed files
- [ ] `unzip`: extract zip archives

**Checksums / encoding / binary inspection**
- [x] `sha256sum`: verify file hash
- [x] `sha512sum`: verify file hash
- [x] `md5sum`: legacy checksum
- [x] `cksum`: POSIX checksum
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
- [ ] `htop`: better process monitor
- [ ] `btop`: even better process monitor
- [x] `bg`: background job
- [x] `fg`: foreground job
- [x] `jobs`: list shell jobs
- [x] `nohup`: survive logout
- [x] `wait`: wait for background jobs
- [ ] `setsid`: run a command in a new session
- [x] `nice`: set priority
- [x] `renice`: change priority
- [x] `timeout`: run with time limit

**Terminal / TTY**
- [x] `stty`: terminal line settings
- [x] `tty`: print current terminal device
- [x] `reset`: reset broken terminal
- [x] `clear`: clear terminal screen
- [x] `script`: record terminal session

**System info**
- [x] `uname`: system info
- [x] `hostname`: hostname
- [x] `uptime`: load/uptime
- [x] `free`: quick memory + swap usage
- [x] `vmstat`: fast CPU, memory, I/O, and run queue snapshot
- [x] `lscpu`: CPU topology and virtualization flags
- [x] `lsmem`: memory layout/topology
- [x] `lsmod`: list loaded kernel modules
- [x] `modprobe`: load/unload kernel modules with dependency handling
- [x] `modinfo`: inspect kernel module metadata
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
- [ ] `cryptsetup`: LUKS disk encryption
- [x] `fdisk`: classic disk partition editor
- [x] `swapon`: enable/list swap devices
- [x] `swapoff`: disable swap devices
- [x] `sync`: flush writes
- [x] `chroot`: run a shell/command with a different root directory
- [ ] `snapper`: filesystem snapshot management

**Networking / connectivity**
- [x] `ip`: addresses, routes, links, and neighbours
- [x] `ss`: sockets, listening ports, and connections
- [x] `ping`: ICMP reachability
- [x] `traceroute`: trace packet path
- [x] `tracepath`: trace path without needing root
- [x] `dig`: DNS lookup
- [x] `nslookup`: older DNS lookup
- [x] `host`: simple DNS lookup
- [ ] `resolvectl`: inspect/query systemd-resolved
- [ ] `curl`: HTTP/API checks
- [x] `wget`: simple downloads

**Network probes / debugging**
- [ ] `nc`: basic TCP/UDP testing
- [ ] `ncat`: richer netcat from nmap
- [ ] `socat`: bidirectional socket/data plumbing
- [ ] `openssl s_client`: TLS endpoint debugging
- [ ] `whois`: domain/IP registry lookup
- [ ] `iperf3`: network throughput measurement
- [ ] `tcpdump`: packet capture
- [ ] `nmap`: host/port discovery
- [ ] `mtr`: ongoing path quality
- [ ] `nethogs`: per-process bandwidth usage
- [ ] `ipcalc`: subnet calculator

**File transfer / sync**
- [x] `rsync`: serious file copy/sync
- [x] `rsync --dry-run`: preview sync safely

**User management**
- [x] `useradd`: create user
- [x] `userdel`: delete user
- [x] `usermod`: modify user
- [x] `groupadd`: create group
- [x] `groupdel`: delete group
- [x] `groupmod`: modify group
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
- [ ] `timedatectl`: time/timezone/NTP state

**Cron / scheduling**
- [x] `crontab`: cron job management

**Package management**
- [ ] `dnf`: Fedora/RHEL package manager
- [ ] `rpm`: low-level rpm operations

**Git**
- [ ] `git`: version control
- [ ] `gitk`: GUI log viewer

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

**Editors**
- [x] `nvim`: your editor
- [x] `vim`: fallback
- [x] `vi`: minimal vim
- [x] `view`: read-only vim
- [ ] `ctags`: generate source navigation tags

**Concepts to learn as concepts, not binaries**
- [ ] shell expansion order
- [x] quoting rules
- [ ] PATH lookup
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
- [ ] mount source vs mount target
- [ ] block device vs filesystem vs mountpoint
- [ ] package ownership: which package installed this file?
- [ ] ODIC and oatuh flow


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
- [ ] `aws`, `jq`, `aws logs tail`, `aws ssm start-session`
- [ ] `aws rds describe-db-instances`, `aws secretsmanager get-secret-value`, `aws kms decrypt`
- [ ] `psql`, `pg_isready`, `pg_dump`, `pg_restore`, `mysql`, `mysqldump`, `mysqladmin`
- [ ] `dig`, `nc`, `openssl s_client` for endpoint/connectivity checks

**If you only internalise a subset first**
- [ ] `fd`, `rg`, `fzf`, `zoxide`, `bat`
- [ ] `jq`, `yq`
- [ ] `rsync`, `just`
- [ ] `watch`, `lsof`
- [ ] `systemctl`, `journalctl`, `ip`, `ss`

**Modern CLI replacements — big quality-of-life wins**
- [ ] `fd`: fast, intuitive find replacement. Pairs with fzf
- [ ] `rg`: ripgrep — fast recursive grep with sane defaults
- [ ] `bat`: cat with syntax highlighting and git integration
- [ ] `fzf`: fuzzy finder — transforms how you navigate
- [ ] `fzf-tmux`: fzf inside tmux panes
- [x] `atuin`: much better shell history/search
- [ ] `zoxide`: smarter cd with frecency tracking
- [ ] `delta`: beautiful git diffs, pairs with lazygit
- [ ] `hyperfine`: benchmark commands properly
- [ ] `btop`: gorgeous process/resource monitor
- [ ] `ncdu`: interactive disk usage explorer — find what's eating space
- [ ] `lazygit`: TUI git client you already use
- [ ] `tree`: directory tree view

**Shell scripting quality**
- [x] `shellcheck`: static analysis for shell scripts — catches real bugs
- [x] `shfmt`: shell script formatter (use with conform.nvim)
- [ ] `bats`: Bash Automated Testing System
- [ ] `envsubst`: substitute env vars in templates — handy for deploy scripts
- [ ] `flock`: prevent overlapping cron/systemd jobs with a lockfile
- [ ] `parallel`: GNU parallel — run jobs in parallel properly

**Repo hygiene / linting**
- [ ] `pre-commit`: run the same local hooks as CI
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

**Terraform / image build**
- [ ] `terraform`: core workflow (`fmt`, `validate`, `plan`, `apply`, `output`, `state`, `console`, `import`)
- [ ] `tofu`: OpenTofu, Terraform-compatible IaC workflow
- [ ] `tflint`: lint Terraform and catch provider-specific mistakes

**Infrastructure debugging**
- [ ] `iostat`: CPU and disk I/O trends (sysstat)
- [ ] `pidstat`: per-process CPU, memory, and I/O (sysstat)
- [ ] `lsof`: what has this file/port/socket open
- [ ] fuser
- [ ] `strace`: (via stap/dtrace) — syscall tracing, find why things hang
- [ ] `iotop`: per-process I/O usage
- [ ] `dmesg`: kernel ring buffer — hardware events, driver issues
- [ ] `dd`: block copy (careful with this one)

**SELinux (Rocky Linux means you deal with this)**
- [ ] `getenforce`: check SELinux mode
- [ ] `sestatus`: SELinux status
- [ ] `setenforce`: set SELinux mode
- [ ] `restorecon`: fix file contexts
- [ ] `audit2why`: explain SELinux denials

**Containers (Fedora native)**
- [ ] `podman`: rootless containers — docker-compatible
- [ ] `docker`: still the lingua franca even if you prefer podman
- [ ] `docker compose`: local multi-container stacks
- [ ] `podman compose`: compose-style podman workflow
- [ ] `skopeo`: inspect/copy container images without pulling
- [ ] `trivy`: image/filesystem/IaC security scanning

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
- [ ] `pg_isready`: fast PostgreSQL readiness/connectivity check
- [ ] `pg_dump`: logical backup of a PostgreSQL database
- [ ] `pg_restore`: restore `pg_dump` custom/directory backups
- [ ] `pg_dumpall`: dump all PostgreSQL databases plus global objects like roles
- [ ] `createdb`: create a PostgreSQL database from the CLI
- [ ] `createuser`: create PostgreSQL roles/users from the CLI
- [ ] `vacuumdb`: run vacuum/analyze/maintenance without opening `psql`
- [ ] `reindexdb`: rebuild indexes when debugging corruption or bloat issues
- [ ] `mysql`: MySQL/MariaDB shell for inspection and admin
- [ ] `mysqldump`: logical backup of a MySQL/MariaDB database
- [ ] `mysqladmin`: quick admin/status operations without opening the full shell
- [ ] `redis-cli`: Redis inspection and debugging
- [ ] `sqlite3`: inspect and query SQLite databases

**Backup/recovery**
- [ ] `restic`: deduplicated encrypted backups
- [x] `rsync`: file sync (also listed in tier 1)

**Process/resource tuning**
- [ ] `sysctl`: kernel parameter tuning
- [ ] `ionice`: I/O priority
- [ ] `taskset`: CPU affinity
- [x] `ulimit`: resource limits
- [ ] `prlimit`: per-process limits

**Logs**
- [ ] `logrotate`: rotate logs
- [ ] `logger`: write message to syslog/journal
- [ ] `lnav`: interactive log viewer for mixed log files and timestamps

**Cloud CLIs**
- [ ] `aws`: AWS CLI
- [ ] `aws-vault`: safer AWS credential handling

**Terminal mail**
- [ ] `mutt`: text-based mail client when staying in the terminal is faster than context-switching to a browser
- [ ] `mail`: minimal text-based mail client for simple send/read flows
- [ ] `mailq`: inspect the local outgoing mail queue

**AWS practical workflows**
- [ ] `aws sts get-caller-identity`: fastest identity/account sanity check
- [ ] `aws sso login`: authenticate with AWS IAM Identity Center / SSO
- [ ] `aws configure sso`: initial SSO profile setup

**Language/runtime tooling**
- [x] `python3`: Python interpreter
- [x] `pip`: Python package installer
- [x] `pipx`: install Python CLI apps cleanly
- [x] `venv`: Python virtual environments
- [x] `node`: JavaScript runtime
- [x] `npm`: Node package manager
- [x] `go`: Go toolchain

**Build / compile basics**
- [x] `make`: build automation
- [x] `gcc`: C compiler
- [x] `ldd`: show shared library dependencies
- [x] `ldconfig`: configure dynamic linker cache
- [x] `pkg-config`: compiler/linker flags for libraries

**Misc high-value**
- [x] `tmux`: terminal multiplexer
- [ ] `watch`: repeat command and watch output
- [ ] `gh`: GitHub CLI

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
- [ ] `pdfinfo`: inspect PDF metadata/page info
- [ ] `qpdf`: inspect, repair, split, merge, and transform PDFs
- [ ] `exiftool`: inspect/edit metadata on documents, images, and media
- [ ] `ocrmypdf`: OCR + PDF optimization — useful for law firm doc scanning
- [ ] `dos2unix`: fix Windows line endings
- [ ] `iconv`: character encoding conversion

**Spell checking / writing**
- [ ] `aspell`: interactive CLI spell checker for prose, notes, and Markdown
- [ ] `hunspell`: dictionary-based spell checker used by many editors and language packs
- [ ] `codespell`: catch common misspellings in code, docs, and config files
- [ ] `typos`: fast repo-wide spell checker for source, filenames, and CI
- [ ] `vale`: prose/style linter for Markdown and documentation
- [ ] `look`: prefix lookup in sorted word lists/dictionaries; handy, but much lower priority than actual spell checkers

**Disk / filesystem edge cases**
- [ ] `udevadm`: inspect devices and udev events/rules

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

**Misc useful**
- [ ] `chafa`: render images in the terminal; handy for quickly inspecting screenshots without leaving the shell
- [ ] `cloc`: count lines of code
- [ ] `croc`: simple encrypted file transfer between machines
- [ ] `jrnl`: simple personal diary app
- [ ] `just`: command runner (you already use this)
- [ ] `stow`: symlink farm manager (your dotfiles)
- [ ] `direnv`: per-directory env vars
- [ ] `xdg-open`: open a file/URL with the desktop default app
- [ ] `pv`: monitor progress through a pipe / long data stream
- [ ] `mods`: AI in the terminal (if you use it)
- [ ] `ollama`: local LLM inference (your GPU passthrough setup)
- [ ] `yt-dlp`: video downloader
- [ ] `rclone`: cloud storage sync (S3, etc.)
- [ ] `terraform-docs`: generate docs for Terraform modules
- [ ] `terraform-ls`: terraform language server
- [ ] `tfsec`: Terraform static security scanning
- [ ] `vagrant`: VM provisioning (your ansible testing)
- [ ] `syncthing`: p2p file sync
- [ ] `jd`: JSON diff
- [ ] `w3m`: terminal web browser
- [ ] `glow`: terminal markdown renderer
- [ ] `cheat`: cheat sheets in terminal
- [ ] `tldr`: short, example-first command docs
- [ ] `cht.sh`: curlable cheat sheets / quick examples

---

## TIER 4: Niche / special-purpose (ignore until relevant)

**X11/Wayland tools**
- [ ] `wl-copy`: Wayland clipboard copy
- [ ] `wl-paste`: Wayland clipboard paste

**Flatpak**
- [ ] `flatpak`: Flatpak package manager
