#ai-written 
# Command Triage: What to Learn vs Ignore

Everything from your system's PATH, categorised.

## TIER 1: Core daily drivers (you almost certainly know these)

**Docs / discovery**
- [ ] `man`: primary system manuals
- [ ] `apropos`: find commands by keyword
- [ ] `whatis`: one-line command descriptions
- [ ] `info`: GNU manuals when `man` is thin

**Shell basics**
- [ ] `bash`: your shell
- [ ] `zsh`: alternative shell (fish also listed) (learn lne editing here)
- [ ] `fish`: friendly interactive shell
- [x] `cd`: change directory
- [x] `pwd`: print working directory
- [x] `ls`: list files
- [x] `dir`: basically ls
- [x] `vdir`: verbose ls
- [x] `cp`: copy - [x] `mv`: move/rename
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
- [ ] `printf`: formatted print
- [ ] `read`: read input in scripts
- [ ] `time`: measure how long a command takes
- [x] `test`: conditional evaluation ([ ])
- [x] `true`: exit 0
- [x] `false`: exit 1
- [x] `yes`: repeat string forever

**Shell language / builtins**
- [x] `type`: show whether something is a shell builtin, alias, function, or binary
- [ ] `help`: shell builtin docs
- [ ] `command`: run command bypassing shell functions/aliases
- [ ] `builtin`: run shell builtin explicitly
- [x] `alias`: define/list aliases
- [x] `unalias`: remove aliases
- [x] `export`: put variables into environment
- [ ] `unset`: remove variable/function
- [ ] `set`: shell options + positional parameters
- [ ] `shopt`: Bash-specific shell options
- [x] `source`: run file in current shell
- [x] `.`: POSIX source
- [ ] `exec`: replace current shell/process
- [ ] `trap`: handle signals/cleanup in scripts
- [ ] `return`: return from function/sourced script
- [ ] `exit`: exit shell/script
- [ ] `shift`: shift positional parameters
- [ ] `getopts`: parse shell script flags
- [ ] `ulimit`: shell resource limits
- [ ] `history`: shell history
- [ ] `fc`: edit/re-run previous commands
- [ ] `bindkey`: zsh keybindings
- [ ] `bind`: bash/readline keybindings

**Text processing**
- [x] `grep`: pattern search
- [x] `egrep`: extended regex grep (deprecated, use grep -E)
- [x] `fgrep`: fixed-string grep (deprecated, use grep -F)
- [ ] `sed`: stream editor
- [ ] `awk`: pattern/action language
- [ ] `gawk`: GNU awk
- [x] `sort`: sort lines
- [x] `uniq`: deduplicate adjacent lines
- [x] `wc`: word/line/byte count
- [x] `cut`: extract fields
- [ ] `tr`: translate/delete characters
- [x] `tee`: split stdout to file + pipe
- [ ] `xargs`: build commands from stdin
- [ ] `diff`: compare files
- [ ] `patch`: apply diffs
- [ ] `comm`: compare sorted files line by line
- [ ] `paste`: merge lines side by side
- [ ] `column`: format into columns
- [ ] `fold`: wrap lines
- [ ] `fmt`: simple text formatter
- [ ] `expand`: tabs to spaces
- [ ] `unexpand`: spaces to tabs
- [ ] `rev`: reverse lines
- [ ] `tac`: reverse file (cat backwards)
- [ ] `nl`: number lines

**File operations**
- [x] `find`: search filesystem
- [x] `chmod`: change permissions
- [x] `chown`: change ownership
- [x] `chgrp`: change group
- [x] `stat`: file metadata
- [x] `file`: detect file type
- [ ] `realpath`: resolve symlinks
- [ ] `readlink`: read symlink target
- [ ] `basename`: strip directory from path
- [ ] `dirname`: strip filename from path
- [ ] `mktemp`: create temp file/dir
- [ ] `install`: copy with permissions
- [ ] `link`: create hard link
- [ ] `unlink`: remove single file

**Permissions / identity / access**
- [x] `umask`: default permissions for newly created files
- [ ] `getfacl`: view POSIX ACLs
- [ ] `setfacl`: set POSIX ACLs
- [ ] `namei`: follow path components and permissions
- [ ] `capsh`: inspect Linux capabilities
- [ ] `getcap`: view file capabilities
- [ ] `setcap`: set file capabilities

**Archiving/compression**
- [x] `tar`: tape archive (tar czf, tar xzf)
- [x] `gzip`: gzip compression
- [x] `gunzip`: decompress gzip
- [x] `zcat`: cat compressed files
- [x] `bzip2`: bzip2 compression
- [x] `xz`: xz compression
- [x] `zip`: create zip archives
- [x] `unzip`: extract zip archives

**Checksums / encoding / binary inspection**
- [ ] `sha256sum`: verify file hash
- [ ] `sha512sum`: verify file hash
- [ ] `md5sum`: legacy checksum
- [ ] `cksum`: POSIX checksum
- [ ] `base64`: encode/decode base64
- [ ] `xxd`: hex dump / reverse hex dump
- [ ] `hexdump`: inspect binary data
- [ ] `strings`: extract printable strings from binaries

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
- [x] `nice`: set priority
- [x] `renice`: change priority
- [ ] `timeout`: run with time limit

**Terminal / TTY**
- [ ] `stty`: terminal line settings
- [ ] `tty`: print current terminal device
- [ ] `reset`: reset broken terminal
- [x] `clear`: clear terminal screen
- [ ] `script`: record terminal session

**System info**
- [ ] `uname`: system info
- [ ] `hostname`: hostname
- [ ] `hostnamectl`: systemd hostname management
- [x] `uptime`: load/uptime
- [ ] `free`: quick memory + swap usage
- [ ] `vmstat`: fast CPU, memory, I/O, and run queue snapshot
- [ ] `lscpu`: CPU topology and virtualization flags
- [ ] `lsmem`: memory layout/topology
- [ ] `nproc`: number of available processing units
- [ ] `date`: date/time
- [ ] `cal`: calendar
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
- [ ] `logname`: original login name
- [ ] `newgrp`: switch current group
- [ ] `chage`: password ageing
- [ ] `getent`: query passwd/group/hosts/services via NSS

**Disk/filesystem**
- [x] `df`: disk free space
- [x] `du`: disk usage
- [x] `mount`: mount filesystems
- [x] `umount`: unmount
- [ ] `mountpoint`: check whether a path is a mountpoint
- [x] `lsblk`: block device list
- [x] `blkid`: filesystem UUIDs/types
- [x] `findmnt`: show mount tree
- [ ] `swapon`: enable/list swap devices
- [ ] `swapoff`: disable swap devices
- [x] `sync`: flush writes

**Networking core**
- [x] `ip`: modern network config (replaces ifconfig)
- [x] `ss`: socket statistics (replaces netstat)
- [x] `ping`: ICMP echo
- [x] `traceroute`: trace packet path
- [x] `tracepath`: similar, no root needed
- [x] `dig`: DNS lookup
- [x] `nslookup`: older DNS lookup
- [x] `host`: simple DNS lookup
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
- [x] `su`: switch user
- [x] `sudo`: execute as root
- [x] `visudo`: edit sudoers safely

**Systemd**
- [ ] `systemctl`: service/unit management
- [ ] `journalctl`: log viewer
- [ ] `loginctl`: session management
- [ ] `timedatectl`: time/timezone
- [ ] `localectl`: locale settings
- [ ] `hostnamectl`: hostname (listed above too)
- [ ] `coredumpctl`: manage core dumps

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
- [ ] `crontab`: cron job management

**Package management**
- [x] `dnf`: Fedora/RHEL package manager
- [x] `rpm`: low-level rpm operations

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
- [ ] `git-receive-pack`: server-side git
- [ ] `git-upload-pack`: server-side git
- [ ] `git-upload-archive`: server-side git
- [ ] `git-shell`: restricted shell for git-only SSH

**SSH**
- [ ] `ssh`: remote shell
- [ ] `mosh`: roaming remote shell for flaky/high-latency connections
- [ ] `scp`: remote copy
- [ ] `sftp`: remote file transfer
- [ ] `ssh-keygen`: key generation
- [ ] `ssh-copy-id`: deploy public key
- [ ] `ssh-agent`: key agent
- [ ] `ssh-add`: add key to agent
- [ ] `ssh-keyscan`: grab host keys
- [ ] `sshd`: SSH daemon
- [ ] `sshpass`: non-interactive SSH password (use keys instead)

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

**Important config locations**
- [x] `/etc/passwd`, `/etc/group`, `/etc/shadow`
- [x] `/etc/sudoers`, `/etc/sudoers.d/`
- [x] `/etc/fstab`
- [x] `/etc/hosts`
- [x] `/etc/resolv.conf`
- [x] `/etc/ssh/sshd_config`
- [x] `/etc/systemd/system/`
- [x] `/usr/lib/systemd/system/`
- [x] `/etc/profile`, `~/.profile`, `~/.bashrc`, `~/.zshrc`
- [x] `/var/log/`
- [x] `/proc/`
- [x] `/sys/`

## TIER 2: High-value tools to invest in learning

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
- [ ] `atuin`: much better shell history/search
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
- [ ] `shellcheck`: static analysis for shell scripts — catches real bugs
- [ ] `shfmt`: shell script formatter (use with conform.nvim)
- [ ] `envsubst`: substitute env vars in templates — handy for deploy scripts
- [ ] `flock`: prevent overlapping cron/systemd jobs with a lockfile
- [ ] `parallel`: GNU parallel — run jobs in parallel properly

**Ansible**
- [ ] `ansible`: ad-hoc automation
- [ ] `ansible-playbook`: run playbooks
- [ ] `ansible-inventory`: inspect inventory
- [ ] `ansible-vault`: encrypted secrets
- [ ] `ansible-galaxy`: roles/collections
- [ ] `ansible-lint`: lint playbooks

**Data wrangling**
- [ ] `jq`: JSON query/transform — essential for API work, terraform state
- [ ] `yq`: YAML equivalent of jq — critical for ansible debugging
- [ ] `column`: (listed above) tabular formatting

**Infrastructure debugging**
- [ ] `lsof`: what has this file/port/socket open
- [ ] `lsfd`: modern file descriptor/socket inspection
- [ ] fuser
- [ ] `inotifywait`: watch file changes/events for automation and debugging
- [ ] `strace`: (via stap/dtrace) — syscall tracing, find why things hang
- [ ] `tcpdump`: packet capture — the ground truth for network issues
- [ ] `nmap`: network scanner/port auditor
- [ ] `ncat`: netcat from nmap — TCP/UDP swiss army knife
- [ ] `arping`: ARP-level ping — find IP conflicts on L2
- [ ] `ethtool`: NIC stats, driver info, link detection
- [ ] `iotop`: per-process I/O usage
- [ ] `nethogs`: per-process bandwidth usage
- [ ] `mtr`: traceroute + ping combined, ongoing
- [ ] `dmesg`: kernel ring buffer — hardware events, driver issues
- [ ] `dmidecode`: hardware inventory from BIOS tables
- [ ] `lshw`: detailed hardware listing
- [ ] `lspci`: PCI devices (GPUs, NICs, storage controllers)
- [ ] `lsusb`: USB devices
- [ ] `smartctl`: disk SMART health data — critical for your RAID setups
- [ ] `hdparm`: disk parameters and benchmarks

**Disk/storage (relevant to your Proxmox + RAID + ZFS work)**
- [ ] `mdadm`: software RAID management
- [ ] `cryptsetup`: LUKS disk encryption
- [ ] `wipefs`: clear filesystem signatures before repurposing disks
- [ ] `blkdiscard`: TRIM/discard entire block device
- [ ] `fstrim`: periodic TRIM for SSDs
- [ ] `resize2fs`: resize ext filesystems
- [ ] `xfs_growfs`: grow XFS filesystem
- [ ] `xfs_repair`: repair XFS
- [ ] `xfs_info`: XFS filesystem info
- [ ] `btrfs`: btrfs management (if you use it on Fedora)
- [ ] `e2fsck`: ext filesystem check
- [ ] `dumpe2fs`: ext filesystem info
- [ ] `dd`: block copy (careful with this one)
- [ ] `losetup`: loop device management

**Firewall/security (directly relevant to your iptables_autoblock work)**
- [ ] `iptables`: legacy packet filtering (your current autoblock script)
- [ ] `iptables-save`: dump rules
- [ ] `iptables-restore`: load rules
- [ ] `ip6tables`: same for IPv6
- [ ] `nft`: nftables — the modern replacement
- [ ] `firewall-cmd`: firewalld CLI
- [ ] `iptables-nft`: iptables syntax over nftables backend
- [ ] `ebtables`: ethernet bridge filtering
- [ ] `ipset`: IP sets for efficient rule matching
- [ ] `arptables`: ARP table filtering

**SELinux (Rocky Linux means you deal with this)**
- [ ] `getenforce`: check SELinux mode
- [ ] `setenforce`: set SELinux mode
- [ ] `sestatus`: SELinux status
- [ ] `semanage`: manage SELinux policy
- [ ] `restorecon`: fix file contexts
- [ ] `chcon`: change file context
- [ ] `setsebool`: set SELinux booleans
- [ ] `getsebool`: get SELinux booleans
- [ ] `audit2allow`: generate policy from denials
- [ ] `audit2why`: explain SELinux denials
- [ ] `semodule`: manage SELinux modules
- [ ] `matchpathcon`: check expected context for path

**Containers (Fedora native)**
- [ ] `podman`: rootless containers — docker-compatible
- [ ] `docker`: still the lingua franca even if you prefer podman
- [ ] `docker compose`: local multi-container stacks
- [ ] `podman compose`: compose-style podman workflow
- [ ] `skopeo`: inspect/copy container images without pulling
- [ ] `lsns`: inspect Linux namespaces
- [ ] `nsenter`: enter container/process namespaces for debugging
- [ ] `unshare`: create a fresh namespace view for testing/isolation
- [ ] `buildah`: (not listed but related) build OCI images
- [ ] `trivy`: image/filesystem/IaC security scanning
- [ ] `crun`: container runtime (low-level)
- [ ] `conmon`: container monitor (low-level)
- [ ] `journalctl -u container-*`: if using podman/systemd units

**Kubernetes**
- [ ] `kubectl`: Kubernetes CLI
- [ ] `helm`: Kubernetes package manager
- [ ] `k9s`: Kubernetes TUI
- [ ] `stern`: tail logs from multiple pods
- [ ] `kustomize`: patch and compose Kubernetes manifests

**Virtualisation (Proxmox/libvirt work)**
- [ ] `virsh`: libvirt CLI — VM management
- [ ] `virt-install`: create VMs
- [ ] `virt-clone`: clone VMs
- [ ] `virt-manager`: GUI VM manager
- [ ] `qemu-img`: disk image creation/conversion
- [ ] `qemu-kvm`: KVM hypervisor
- [ ] `qemu-system-x86_64`: full system emulator

**Certificate/TLS (relevant to your Caddy + internal PKI work)**
- [ ] `openssl`: cert inspection, CSR generation, TLS debugging
- [ ] `certtool`: GnuTLS cert tool
- [ ] `trust`: manage system trust store
- [ ] `update-ca-trust`: refresh CA bundle
- [ ] `p11-kit`: PKCS#11 module management

**Secrets / credentials**
- [ ] `gpg`: encryption/signing
- [ ] `pass`: Unix password manager
- [ ] `bw`: Bitwarden CLI
- [ ] `age`: modern file encryption
- [ ] `sops`: encrypted config/secrets, often with age/KMS

**Backup/recovery (your ReaR + restic stack)**
- [ ] `rear`: Relax-and-Recover — bare metal DR
- [ ] `restic`: deduplicated encrypted backups
- [ ] `rsync`: file sync (also listed in tier 1)

**Samba/CIFS (law firm Windows interop)**
- [ ] `smbclient`: SMB file access
- [ ] `mount.cifs`: mount SMB shares
- [ ] `cifscreds`: manage CIFS credentials
- [ ] `smbcacls`: SMB ACLs

**NFS (if used between Proxmox nodes)**
- [ ] `mount.nfs`: NFS mount
- [ ] `mount.nfs4`: NFSv4 mount
- [ ] `nfsstat`: NFS statistics
- [ ] `showmount`: list NFS exports
- [ ] `exportfs`: manage NFS exports
- [ ] `rpcinfo`: RPC service info

**LVM (likely on your OVH servers)**
- [ ] `pvcreate`: create physical volume
- [ ] `vgcreate`: create volume group
- [ ] `lvcreate`: create logical volume
- [ ] `pvs`: list PVs
- [ ] `vgs`: list VGs
- [ ] `lvs`: list LVs
- [ ] `pvdisplay`: PV detail
- [ ] `vgdisplay`: VG detail
- [ ] `lvdisplay`: LV detail
- [ ] `lvextend`: grow LV
- [ ] `lvresize`: resize LV
- [ ] `lvremove`: delete LV
- [ ] `vgextend`: add PV to VG

**Process/resource tuning**
- [ ] `sysctl`: kernel parameter tuning
- [ ] `ionice`: I/O priority
- [ ] `taskset`: CPU affinity
- [ ] `ulimit`: resource limits
- [ ] `prlimit`: per-process limits
- [ ] `coresched`: core scheduling
- [ ] `chrt`: real-time scheduling

**Boot / kernel / initramfs**
- [ ] `grubby`: manage default kernel/boot args on Fedora/RHEL
- [ ] `dracut`: build initramfs
- [ ] `lsinitrd`: inspect initramfs
- [ ] `bootctl`: systemd-boot management, where relevant
- [ ] `efibootmgr`: UEFI boot entries

**Audit/logging (server hardening)**
- [ ] `auditctl`: audit rule management
- [ ] `auditd`: audit daemon
- [ ] `aureport`: audit reports
- [ ] `ausearch`: search audit logs
- [ ] `augenrules`: generate audit rules from files

**Logs**
- [ ] `logrotate`: rotate logs
- [ ] `logger`: write message to syslog/journal

**Cloud CLIs**
- [ ] `aws`: AWS CLI
- [ ] `aws-vault`: safer AWS credential handling
- [ ] `gcloud`: Google Cloud CLI
- [ ] `az`: Azure CLI

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

**Text/doc conversion**
- [ ] `pandoc`: universal doc converter — markdown to PDF, docx, etc.
- [ ] `img2pdf`: images to PDF
- [ ] `ocrmypdf`: OCR + PDF optimization — useful for law firm doc scanning
- [ ] `tesseract`: OCR engine behind ocrmypdf
- [ ] `dos2unix`: fix Windows line endings
- [ ] `unix2dos`: create Windows line endings
- [ ] `iconv`: character encoding conversion
- [ ] `uchardet`: detect character encoding

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
- [ ] `nmcli`: NetworkManager CLI
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
- [ ] `anacron`: run missed cron jobs
- [ ] `at`: one-shot scheduled command
- [ ] `atq`: list at queue
- [ ] `atrm`: remove at job
- [ ] `batch`: run when load is low

**Mail/server notifications**
- [ ] `mailx`: send/read simple mail
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
- [ ] `cloc`: count lines of code
- [ ] `croc`: simple encrypted file transfer between machines
- [ ] `jrnl`: simple personal diary app
- [ ] `just`: command runner (you already use this)
- [ ] `stow`: symlink farm manager (your dotfiles)
- [ ] `direnv`: per-directory env vars
- [ ] `pv`: monitor progress through a pipe / long data stream
- [ ] `mods`: AI in the terminal (if you use it)
- [ ] `ollama`: local LLM inference (your GPU passthrough setup)
- [ ] `yt-dlp`: video downloader
- [ ] `rclone`: cloud storage sync (S3, etc.)
- [ ] `terraform`: infrastructure as code (your stack)
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
