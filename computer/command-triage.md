#ai-written 
# Command Triage: What to Learn vs Ignore

Everything from your system's PATH, categorised.

- First of all learn meta commands like man and apropos.
## TIER 1: Core daily drivers (you almost certainly know these)

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
- [x] `test`: conditional evaluation ([ ])
- [x] `true`: exit 0
- [x] `false`: exit 1
- [x] `yes`: repeat string forever

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
- [ ] `find`: search filesystem
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

**Archiving/compression**
- [x] `tar`: tape archive (tar czf, tar xzf)
**Process management**
- [x] `ps`: process list
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

**System info**
- [ ] `uname`: system info
- [ ] `hostname`: hostname
- [ ] `hostnamectl`: systemd hostname management
- [x] `uptime`: load/uptime
- [ ] `date`: date/time
- [ ] `cal`: calendar
- [x] `who`: logged in users
- [x] `whoami`: current user
- [x] `id`: user/group IDs
- [ ] `groups`: group membership
- [x] `env`: environment variables
- [x] `printenv`: print env vars

**Disk/filesystem**
- [x] `df`: disk free space
- [x] `du`: disk usage
- [x] `mount`: mount filesystems
- [x] `umount`: unmount
- [x] `lsblk`: block device list
- [x] `blkid`: filesystem UUIDs/types
- [x] `findmnt`: show mount tree
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

**Package management**
- [x] `dnf`: Fedora/RHEL package manager
- [x] `rpm`: low-level rpm operations

**Git**
- [ ] `git`: version control
- [ ] `gitk`: GUI log viewer
- [ ] `git-receive-pack`: server-side git
- [ ] `git-upload-pack`: server-side git
- [ ] `git-upload-archive`: server-side git
- [ ] `git-shell`: restricted shell for git-only SSH

**SSH**
- [ ] `ssh`: remote shell
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

## TIER 2: High-value tools to invest in learning

**Modern CLI replacements — big quality-of-life wins**
- [ ] `fd`: fast, intuitive find replacement. Pairs with fzf
- [ ] `rg`: ripgrep — fast recursive grep with sane defaults
- [ ] `bat`: cat with syntax highlighting and git integration
- [ ] `fzf`: fuzzy finder — transforms how you navigate
- [ ] `fzf-tmux`: fzf inside tmux panes
- [ ] `zoxide`: smarter cd with frecency tracking
- [ ] `delta`: beautiful git diffs, pairs with lazygit
- [ ] `btop`: gorgeous process/resource monitor
- [ ] `ncdu`: interactive disk usage explorer — find what's eating space
- [ ] `lazygit`: TUI git client you already use
- [ ] `tree`: directory tree view

**Shell scripting quality**
- [ ] `shellcheck`: static analysis for shell scripts — catches real bugs
- [ ] `shfmt`: shell script formatter (use with conform.nvim)
- [ ] `envsubst`: substitute env vars in templates — handy for deploy scripts
- [ ] `parallel`: GNU parallel — run jobs in parallel properly

**Data wrangling**
- [ ] `jq`: JSON query/transform — essential for API work, terraform state
- [ ] `yq`: YAML equivalent of jq — critical for ansible debugging
- [ ] `column`: (listed above) tabular formatting

**Infrastructure debugging**
- [ ] `lsof`: what has this file/port/socket open
- [ ] fuser
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
- [ ] `skopeo`: inspect/copy container images without pulling
- [ ] `buildah`: (not listed but related) build OCI images
- [ ] `crun`: container runtime (low-level)
- [ ] `conmon`: container monitor (low-level)

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

**Audit/logging (server hardening)**
- [ ] `auditctl`: audit rule management
- [ ] `auditd`: audit daemon
- [ ] `aureport`: audit reports
- [ ] `ausearch`: search audit logs
- [ ] `augenrules`: generate audit rules from files

**Misc high-value**
- [ ] `tmux`: terminal multiplexer
- [ ] `screen`: (not listed but tmux is better)
- [ ] `watch`: repeat command and watch output
- [ ] `ipcalc`: subnet calculator
- [ ] `openconnect`: VPN client (if you use it)
- [ ] `chronyc`: NTP client management
- [ ] `timedatectl`: (listed above) time sync status

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

**Cron / scheduling**
- [ ] `crontab`: (tier 1 really) cron job management
- [ ] `anacron`: run missed cron jobs
- [ ] `at`: one-shot scheduled command
- [ ] `atq`: list at queue
- [ ] `atrm`: remove at job
- [ ] `batch`: run when load is low

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
- [ ] `just`: command runner (you already use this)
- [ ] `stow`: symlink farm manager (your dotfiles)
- [ ] `direnv`: per-directory env vars
- [ ] `mods`: AI in the terminal (if you use it)
- [ ] `ollama`: local LLM inference (your GPU passthrough setup)
- [ ] `gh`: GitHub CLI
- [ ] `yt-dlp`: video downloader
- [ ] `rclone`: cloud storage sync (S3, etc.)
- [ ] `terraform`: infrastructure as code (your stack)
- [ ] `terraform-ls`: terraform language server
- [ ] `vagrant`: VM provisioning (your ansible testing)
- [ ] `syncthing`: p2p file sync
- [ ] `jd`: JSON diff
- [ ] `w3m`: terminal web browser
- [ ] `glow`: terminal markdown renderer
- [ ] `cheat`: cheat sheets in terminal

---

## TIER 4: Niche / special-purpose (ignore until relevant)

**X11/Wayland tools**
- [ ] `wl-copy`: Wayland clipboard copy
- [ ] `wl-paste`: Wayland clipboard paste

**Flatpak**
- [ ] `flatpak`: Flatpak package manager
