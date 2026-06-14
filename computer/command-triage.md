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
- [ ] `zsh`: alternative shell (fish also listed) (learn lne editing here)
- [x] `fish`: friendly interactive shell
- [x] `cd`: change directory
- [x] `pwd`: print working directory
- [x] `ls`: list files
- [x] `dir`: basically ls
- [x] `vdir`: verbose ls
- [x] `cp`: copy 
- [x] `mv`: move/rename
 - [x] `rm`: remove
- [x] `rmdir`: remove empty dirs
- [x] `mkdir`: make dirs
- [x] `ln`: links (hard + symlinks)
- [x] `touch`: create/update timestamps
- [x] `cat`: concatenate/display files
- [x] `less`: pager
- [x] `more`: worse pager
- [x] `head`: first N lines
- [x] `tail`: last N lines (tail -f for log following)
- [x] `echo`: print text
- [x] `printf`: formatted print
- [x] `read`: read input in scripts
- [x] `time`: measure how long a command takes
- [x] `test`: conditional evaluation ([ ])
- [x] `true`: exit 0Unlike something like Kubernetes or Neovim, tmux does not have a massive evolving abstraction stack on top of it. The architecture is stable, small, and old-school Unix-y.


- [x] `false`: exit 1
- [x] `yes`: repeat string forever
- [x] `sleep`: delay for a fixed duration
- [x] `seq`: generate numeric sequences for loops, filenames, and quick tsed is worth learning to fluency in its core operations. But awk rewards going further, because it remains readable much longer. Variables, arrays, fields, BEGIN, END, conditions, formatted printing: these are all genuinely useful rather than “look upon my hold-space incantation and despair.”

est data

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
- [x] `egrep`: extended regex grep (deprecated, use grep -E)
- [x] `fgrep`: fixed-string grep (deprecated, use grep -F)
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
[]()
**Archiving/compression**
- [ ] `tar`: tape archive (tar czf, tar xzf)
- [ ] `gzip`: gzip compression
- [ ] `gunzip`: decompress gzip
- [x] `zcat`: cat compressed files
- [x] `bzip2`: bzip2 compression
- [x] `xz`: xz compression
- [x] `zip`: create zip archives
- [x] `unzip`: extract zip archives
- [x] `zstd`: modern fast compression
- [x] `zstdcat`: stream decompressed zstd data
- [x] `zipinfo`: inspect zip archive contents/metadata
- [x] `7z`: handle 7-Zip and many archive formats

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
- [ ] `hwclock`: inspect/set hardware clock
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
- [x] `chage`: password ageing
- [ ] `getent`: query passwd/group/hosts/services via NSS

**Disk/filesystem**
- [x] `df`: disk free space
- [x] `du`: disk usage
- [x] `mount`: mount filesystems
- [x] `umount`: unmount
- [x] `mountpoint`: check whether a path is a mountpoint
- [x] `lsblk`: block device list
- [x] `blkid`: filesystem UUIDs/types
- [x] `findmnt`: show mount tree
- [ ] `fdisk`: classic disk partition editor
- [ ] `parted`: partition editor, especially for GPT workflows
- [ ] `mkfs`: create filesystems
- [ ] `fsck`: check/repair filesystems
- [x] `swapon`: enable/list swap devices
- [x] `swapoff`: disable swap devices
- [ ] `mkswap`: initialise swap space
- [x] `sync`: flush writes

**Networking core**
- [x] `ip`: modern network config (replaces ifconfig)
- [x] `ss`: socket statistics (replaces netstat)
- [x] `ping`: ICMP echo
- [x] `traceroute`: trace packet path
- [x] `tracepath`: similar, no root needed
- [x] `dig`: DNS lookup
- [x] `nslookup`: older DNS lookup
- [x] `host`: simple D￼￼￼￼￼ ￼￼pg_restore￼￼: restore ￼￼pg_dump￼￼ custom/directory backupsNS lookup
- [ ] `curl`: HTTP client
- [x] `wget`: download files

**DNS / resolver debugging**
- [ ] `resolvectl`: inspect/query systemd-resolved
- [ ] `getent hosts`: resolve through the system NSS stack
- [ ] `getent ahosts`: show IPv4/IPv6 address resolution

**Network utilities**
- [ ] `nc`: netcat, basic TCP/UDP testing
- [ ] `ncat`: nmap's better netcat
- [ ] `socat`: bidirectional data relay, socket plumbing
- [ ] `openssl s_client`: TLS connection debugging
- [ ] `whois`: domain/IP registry lookup
- [ ] `iperf3`: measure network throughput and diagnose path issues
- [ ] `nmcli`: NetworkManager CLI

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
- [ ] `chfn`: change a user's GECOS/full-name information
- [x] `chsh`: change a user's login shell
- [x] `su`: switch user
- [x] `sudo`: execute as root
- [x] `visudo`: edit sudoers safely
- [x] `sudoedit`: edit root-owned files safely through sudo
- [x] `vipw`: safely edit `/etc/passwd` and related account files
- [x] `vigr`: safely edit `/etc/group` and related group files

**Systemd**
- [ ] `systemctl`: service/unit management
- [ ] `journalctl`: log viewer
- [ ] `loginctl`: session management
- [ ] `timedatectl`: time/timezone
- [ ] `localectl`: locale settings
- [ ] `hostnamectl`: hostname (listed above too)
- [ ] `coredumpctl`: manage core dumps
- [ ] `shutdown`: schedule or trigger shutdown/reboot on modern systemd systems
- [ ] `reboot`: trigger an immediate reboot
- [ ] `poweroff`: power the system down immediately

**Systemd practical extras**
- [ ] `systemctl status`
- [ ] `systemctl list-units`
- [ ] `systemctl cat`
- [ ] `systemctl edit`
- [ ] `systemctl daemon-reload`
- [ ] `systemd-delta`: compare local unit overrides against vendor units
- [ ] `journalctl -u`
- [ ] `journalctl -b`
- [ ] `journalctl -f`

**Cron / scheduling**
- [x] `crontab`: cron job management

**Package management**
- [ ] `dnf`: Fedora/RHEL package manager
- [ ] `rpm`: low-level rpm operations

**Fedora/RHEL package tooling**
- [ ] `dnf repoquery`: query packages/repos
- [ ] `dnf provides`: find package that owns a file/command
- [ ] `rpm -qf`: find which package owns a file
- [ ] `rpm -ql`: list package files
- [ ] `rpm -qc`: list config files from package
- [ ] `rpm -V`: verify package-installed files

**Git**
- [ ] `git`: version control
- [ ] `gitk`: GUI log viewer
- [ ] `git reflog`: recover from bad moves and find previous branch/head states
- [ ] `git bisect`: binary-search for the commit that introduced a bug
- [ ] `git worktree`: keep multiple checkouts of one repo
- [ ] `git stash`: temporary work-in-progress storage
- [ ] `git rebase`: rewrite/replay commits deliberately
- [ ] `git cherry-pick`: copy specific commits between branches
- [ ] `git blame`: inspect line-level authorship/history
- [ ] `git restore`: restore paths from index/commits without old `checkout` ambiguity
- [ ] `git switch`: switch branches without old `checkout` ambiguity

**SSH**
- [x] `ssh`: remote shell
- [ ] `mosh`: roaming remote shell for flaky/high-latency connections
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

**Concepts to learn as concepts, not binaries**
- [ ] shell expansion order
- [x] quoting rules
- [ ] PATH lookup
- [ ] Kubernetes model: pods, deployments, services, ingress, secrets, volumes
- [ ] fast doc lookup: official docs first, then `site:` search by tool/vendor
- [ ] Terraform lookup model: language docs vs provider docs vs registry module docs
- [ ] browser keyword search shortcuts / DevDocs for fast web-doc lookup
- [ ] login/session chain: `systemd` -> `getty` -> `login` -> shell/session
- [ ] boot/initramfs/rescue chain: kernel -> initramfs -> `systemd` -> units
- [ ] cgroups vs namespaces vs systemd units
- [ ] systemd unit lifecycle
- [ ] journalctl query model
- [ ] file ownership vs permissions vs ACLs
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
- [ ] `dig`, `getent hosts`, `nc`, `openssl s_client` for endpoint/connectivity checks

**If you only internalise a subset first**
- [ ] `fd`, `rg`, `fzf`, `zoxide`, `bat`
- [ ] `jq`, `yq`
- [ ] `rsync`, `just`
- [ ] `watch`, `lsof` or `lsfd`
- [ ] `systemctl`, `journalctl`, `ip`, `ss`

**Modern CLI replacements — big quality-of-life wins**
- [ ] `fd`: fast, intuitive find replacement. Pairs with fzf
- [ ] `rg`: ripgrep — fast recursive grep with sane defaults
- [ ] `bat`: cat with syntax highlighting and git integration
- [ ] `eza`: modern `ls` replacement
- [ ] `fzf`: fuzzy finder — transforms how you navigate
- [ ] `fzf-tmux`: fzf inside tmux panes
- [x] `atuin`: much better shell history/search
- [ ] `zoxide`: smarter cd with frecency tracking
- [ ] `delta`: beautiful git diffs, pairs with lazygit
- [ ] `hyperfine`: benchmark commands properly
- [ ] `sd`: simpler search/replace than `sed`
- [ ] `duf`: nicer `df`
- [ ] `dust`: nicer `du`
- [ ] `procs`: nicer `ps`
- [ ] `xh`: friendlier HTTP client than `curl`
- [ ] `zellij`: modern terminal workspace/multiplexer
- [ ] `btop`: gorgeous process/resource monitor
- [ ] `btm`: another modern process/resource monitor (`bottom`)
- [ ] `ncdu`: interactive disk usage explorer — find what's eating space
- [ ] `lazygit`: TUI git client you already use
- [ ] `tree`: directory tree view

**Shell scripting quality**
- [x] `shellcheck`: static analysis for shell scripts — catches real bugs
- [x] `shfmt`: shell script formatter (use with conform.nvim)
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
- [ ] `packer`: build AMIs and other machine images

**Infrastructure debugging**
- [ ] `iostat`: CPU and disk I/O trends (sysstat)
- [ ] `mpstat`: per-CPU usage and steal time (sysstat)
- [ ] `pidstat`: per-process CPU, memory, and I/O (sysstat)
- [ ] `sar`: historical system activity from sysstat
- [ ] `lsof`: what has this file/port/socket open
- [ ] `lsfd`: modern file descriptor/socket inspection
- [ ] fuser
- [ ] `inotifywait`: watch file changes/events for automation and debugging
- [ ] `strace`: (via stap/dtrace) — syscall tracing, find why things hang
- [ ] `tcpdump`: packet capture — the ground truth for network issues
- [ ] `nmap`: network scanner/port auditor
- [ ] `ncat`: netcat from nmap — TCP/UDP swiss army knife
- [ ] `iotop`: per-process I/O usage
- [ ] `mtr`: traceroute + ping combined, ongoing
- [ ] `dmesg`: kernel ring buffer — hardware events, driver issues
- [ ] `dd`: block copy (careful with this one)

**Firewall/security (directly relevant to your iptables_autoblock work)**
- [ ] `iptables`: legacy packet filtering (your current autoblock script)
- [ ] `iptables-save`: dump rules
- [ ] `iptables-restore`: load rules
- [ ] `ip6tables`: same for IPv6
- [ ] `nft`: nftables — the modern replacement
- [ ] `firewall-cmd`: firewalld CLI
- [ ] `iptables-nft`: iptables syntax over nftables backend
- [ ] `ipset`: IP sets for efficient rule matching

**SELinux (Rocky Linux means you deal with this)**
- [ ] `getenforce`: check SELinux mode
- [ ] `sestatus`: SELinux status
- [ ] `restorecon`: fix file contexts
- [ ] `audit2why`: explain SELinux denials

**Containers (Fedora native)**
- [ ] `podman`: rootless containers — docker-compatible
- [ ] `docker`: still the lingua franca even if you prefer podman
- [ ] `docker compose`: local multi-container stacks
- [ ] `podman compose`: compose-style podman workflow

**Certificate/TLS (relevant to your Caddy + internal PKI work)**
- [ ] `openssl`: cert inspection, CSR generation, TLS debugging
- [ ] `trust`: manage system trust store
- [ ] `update-ca-trust`: refresh CA bundle

**Secrets / credentials**
- [ ] `gpg`: encryption/signing
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

**Backup/recovery (your ReaR + restic stack)**
- [ ] `rear`: Relax-and-Recover — bare metal DR
- [ ] `restic`: deduplicated encrypted backups
- [x] `rsync`: file sync (also listed in tier 1)

**Samba/CIFS (law firm Windows interop)**
- [ ] `smbclient`: SMB file access
- [ ] `mount.cifs`: mount SMB shares
- [ ] `cifscreds`: manage CIFS credentials
- [ ] `smbcacls`: SMB ACLs

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
- [x] `gcloud`: Google Cloud CLI
- [x] `az`: Azure CLI

**Terminal mail**
- [ ] `mutt`: text-based mail client when staying in the terminal is faster than context-switching to a browser
- [ ] `mail`: minimal text-based mail client for simple send/read flows
- [ ] `mailq`: inspect the local outgoing mail queue

**AWS practical workflows**
- [ ] `aws sts get-caller-identity`: fastest identity/account sanity check
- [ ] `aws sso login`: authenticate with AWS IAM Identity Center / SSO
- [ ] `aws configure sso`: initial SSO profile setup
- [ ] `aws configure list-profiles`: list configured AWS profiles
- [ ] `aws s3 ls`: quick bucket/object listing sanity checks
- [ ] `aws s3 cp`: ad hoc uploads/downloads and one-off copies
- [ ] `aws s3 sync`: sync directories to or from S3 safely
- [ ] `aws ssm start-session`: shell access without SSH bastions/keys
- [ ] `aws ssm send-command`: run remote commands through SSM
- [ ] `aws logs tail`: follow CloudWatch logs from the CLI
- [ ] `aws ecr get-login-password`: authenticate to ECR
- [ ] `aws ecr describe-images`: inspect pushed image tags and digests
- [ ] `aws ec2 describe-instances`: inspect EC2 state and metadata
- [ ] `aws ec2 describe-security-groups`: inspect firewall rules and attached groups
- [ ] `aws ec2 describe-network-interfaces`: inspect ENIs, private IPs, and attachments
- [ ] `aws rds describe-db-instances`: inspect RDS instance state and endpoints
- [ ] `aws route53 list-resource-record-sets`: inspect DNS records
- [ ] `aws acm list-certificates`: inspect certificate inventory
- [ ] `aws elbv2 describe-target-health`: debug target group health
- [ ] `aws elbv2 describe-listeners`: inspect listener ports, certificates, and actions
- [ ] `aws elbv2 describe-rules`: inspect listener rules and routing conditions
- [ ] `aws cloudfront create-invalidation`: flush cached objects after deploys
- [ ] `aws autoscaling describe-auto-scaling-groups`: inspect autoscaling state
- [ ] `aws secretsmanager get-secret-value`: inspect secret values/versions
- [ ] `aws kms decrypt`: debug KMS-backed secret workflows

**ECS / Fargate (if used)**
- [ ] `aws ecs update-service`: deploy or roll a service
- [ ] `aws ecs describe-services`: inspect service state/events
- [ ] `aws ecs execute-command`: shell/command into a running task
- [ ] `aws ecs list-tasks`: enumerate running/stopped tasks
- [ ] `aws ecs describe-tasks`: inspect task state and failures

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
- [x] `screen`: (not listed but tmux is better)
- [ ] `watch`: repeat command and watch output
- [ ] `ipcalc`: subnet calculator
- [ ] `gh`: GitHub CLI
- [x] `openconnect`: VPN client (if you use it)
- [ ] `chronyc`: NTP client management

---

## TIER 3: Good to know exist, learn when needed

**Shell / legacy scripting**
- [ ] `expr`: legacy arithmetic/string evaluator you still see in older shell scripts

**CLI calculators**
- [ ] `bc`: arbitrary-precision calculator for shell math, unit conversions, and quick ops arithmetic
- [ ] `dc`: reverse-polish stack calculator; mostly worth recognizing rather than prioritizing

**Text/doc conversion**
- [x] `pandoc`: universal doc converter — markdown to PDF, docx, etc.
- [ ] `pdftotext`: extract text from PDFs
- [ ] `pdfinfo`: inspect PDF metadata/page info
- [ ] `qpdf`: inspect, repair, split, merge, and transform PDFs
- [ ] `exiftool`: inspect/edit metadata on documents, images, and media
- [ ] `magick`: ImageMagick entry point for image conversion and manipulation
- [ ] `img2pdf`: images to PDF
- [ ] `ocrmypdf`: OCR + PDF optimization — useful for law firm doc scanning
- [ ] `tesseract`: OCR engine behind ocrmypdf
- [ ] `dos2unix`: fix Windows line endings
- [ ] `unix2dos`: create Windows line endings
- [ ] `iconv`: character encoding conversion
- [ ] `uchardet`: detect character encoding

**Spell checking / writing**
- [ ] `aspell`: interactive CLI spell checker for prose, notes, and Markdown
- [ ] `hunspell`: dictionary-based spell checker used by many editors and language packs
- [ ] `codespell`: catch common misspellings in code, docs, and config files
- [ ] `typos`: fast repo-wide spell checker for source, filenames, and CI
- [ ] `vale`: prose/style linter for Markdown and documentation
- [ ] `look`: prefix lookup in sorted word lists/dictionaries; handy, but much lower priority than actual spell checkers

**Network situational**
- [ ] `bridge`: bridge management
- [ ] `tc`: traffic control (QoS)
- [ ] `dcb`: data centre bridging
- [ ] `devlink`: devlink device management
- [ ] `rdma`: RDMA management
- [ ] `vdpa`: vDPA management
- [ ] `tipc`: TIPC protocol
- [ ] `iw`: wireless config
- [ ] `wpa_cli`: WPA supplicant control
- [ ] `wpa_supplicant`: WPA auth daemon
- [ ] `nm-online`: wait for network
- [ ] `rfkill`: enable/disable radios
- [ ] `dnsmasq`: lightweight DNS/DHCP server
- [ ] `avahi-daemon`: mDNS/DNS-SD daemon
- [ ] `avahi-browse`: browse mDNS services
- [ ] `avahi-resolve`: resolve mDNS names

**Disk / filesystem edge cases**
- [ ] `badblocks`: scan for bad blocks
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

**Systemd extended**
- [ ] `systemd-analyze`: boot performance analysis
- [ ] `systemd-cgls`: cgroup tree
- [ ] `systemd-cgtop`: cgroup resource usage
- [ ] `systemd-run`: transient units
- [ ] `systemd-nspawn`: lightweight container
- [ ] `systemd-resolve`: DNS resolution debugging (resolvectl)
- [ ] `systemd-cat`: pipe to journal
- [ ] `systemd-escape`: escape strings for unit names
- [ ] `systemd-tmpfiles`: manage temp files
- [ ] `systemd-sysusers`: manage system users declaratively
- [ ] `systemd-mount`: mount via systemd
- [ ] `systemd-dissect`: inspect disk images
- [ ] `systemd-creds`: credential management
- [ ] `systemd-cryptenroll`: LUKS2 token enrollment
- [ ] `systemd-repart`: declarative partitioning
- [ ] `systemd-detect-virt`: detect virtualisation type
- [ ] `machinectl`: manage containers/VMs (systemd-nspawn)
- [ ] `portablectl`: portable services
- [ ] `homectl`: systemd-homed user management
- [ ] `importctl`: import VM/container images
- [ ] `resolvectl`: DNS resolver management

**Quota management (multi-tenant servers)**
- [ ] `quota`: show quotas
- [ ] `quotacheck`: scan filesystem for quotas
- [ ] `quotaon`: enable quotas
- [ ] `quotaoff`: disable quotas
- [ ] `edquota`: edit user quotas
- [ ] `repquota`: quota report
- [ ] `setquota`: set quota non-interactively

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
