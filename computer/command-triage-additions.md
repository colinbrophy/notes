- [ ] **WE HAVE AUDITED THIS FILE: WE HAVE DECIDED WHAT NEEDS TO BE EAGERLY LEARNT; DO NOT AUDIT IT AGAIN.**

#ai-written
# Command Triage Additions

Companion note for practical omissions from [[command-triage]]. These are candidates to fold into the main triage later, not a claim that every command deserves equal study.

## Core Unix / Userland

### Shells / Legacy Commands

- [ ] `fish`: friendly interactive shell
- [ ] `dir`: basically `ls`
- [ ] `vdir`: verbose `ls`
- [ ] `more`: older pager, mostly superseded by `less`
- [ ] `mknod`: create device nodes/FIFOs manually
- [ ] `csplit`: split files by context/pattern
- [ ] `tsort`: topological sort
- [ ] `setpriv`: run a program with modified Linux privileges

### Basic System Oddities

- [ ] `arch`: print machine architecture, similar to `uname -m`
- [ ] `factor`: factor integers; mostly a curiosity, occasionally useful for quick maths
- [ ] `hostid`: print numeric host identifier
- [ ] `shred`: overwrite a file before deleting it; useful to recognise, limited on SSDs/COW filesystems
- [ ] `cpio`: archive format/tool still seen in initramfs and legacy Unix contexts

### Text / Diff / Encoding

- [ ] `egrep`: extended regex grep; deprecated, use `grep -E`
- [ ] `fgrep`: fixed-string grep; deprecated, use `grep -F`
- [ ] `dircolors`: configure `ls` colour output
- [ ] `pcre2grep`: grep using PCRE2 regular expressions
- [ ] `pcre2test`: test/debug PCRE2 regular expressions
- [ ] `md5sum`: legacy checksum
- [ ] `cksum`: POSIX checksum
- [ ] `sum`: old checksum tool; recognise, prefer stronger hashes
- [ ] `b2sum`: BLAKE2 checksums
- [x] `base32`: base32 encode/decode
- [ ] `basenc`: encode/decode base16/base32/base64 variants
- [ ] `col`: filter reverse line feeds from old formatter output
- [ ] `colrm`: remove columns from text
- [ ] `uconv`: Unicode conversion/transliteration tool
- [ ] `ul`: render underlining for terminals
- [ ] `unicode_start`: switch console to Unicode mode
- [ ] `unicode_stop`: leave console Unicode mode
- [ ] `unix2mac`: convert Unix line endings to old Mac line endings
- [ ] `mac2unix`: convert old Mac line endings to Unix line endings
- [ ] `diffstat`: summarise patch/diff size by file
- [ ] `combinediff`: combine incremental patches
- [ ] `dehtmldiff`: make HTML diffs easier to read as plain diffs

### Compression / Archives

- [ ] `bzip2`: bzip2 compression
- [ ] `xz`: xz compression
- [ ] `zip`: create zip archives
- [ ] `zstd`: modern fast compression
- [ ] `zstdcat`: stream decompressed zstd data
- [ ] `zipinfo`: inspect zip archive contents/metadata
- [ ] `7z`: handle 7-Zip and many archive formats
- [ ] `zstdgrep`: grep compressed zstd files
- [ ] `zstdless`: page compressed zstd files
- [ ] `lz4`: very fast compression
- [ ] `lz4cat`: stream decompressed lz4 data
- [ ] `xzcat`: stream decompressed xz data
- [ ] `bzcat`: stream decompressed bzip2 data

### Process / Scheduling

- [ ] `setsid`: run a command in a new session
- [ ] `coresched`: core scheduling
- [ ] `chrt`: real-time scheduling

### Modern CLI Replacements

- [ ] `choose`: human-friendly field selection, lighter than `cut`/`awk`
- [ ] `sd`: simpler search/replace than `sed`
- [ ] `duf`: nicer `df`
- [ ] `dust`: nicer `du`
- [ ] `procs`: nicer `ps`
- [ ] `xh`: friendlier HTTP client than `curl`

### Git Server Plumbing

- [ ] `git-receive-pack`: server-side git
- [ ] `git-upload-pack`: server-side git
- [ ] `git-upload-archive`: server-side git
- [ ] `git-shell`: restricted shell for git-only SSH

### Git Tools

- [ ] `tig`: terminal Git history/browser
- [ ] `gitui`: terminal Git UI
- [ ] `git-lfs`: Git Large File Storage for repos with large binary assets
- [ ] `git-filter-repo`: rewrite Git history for cleanup, splitting, or secret removal

### Git Commands Worth Recognising

- [ ] `git rev-list`: list commits programmatically
- [ ] `git cat-file`: inspect raw Git objects
- [ ] `git ls-tree`: inspect tree contents at a commit
- [ ] `git for-each-ref`: script over branches, tags, and refs
- [ ] `git update-index`: manipulate index flags, e.g. assume-unchanged/skip-worktree
- [ ] `git bundle`: package Git history into a single file for offline transfer
- [ ] `git credential`: inspect/use credential helpers
- [ ] `git maintenance`: newer background maintenance command
- [ ] `git notes`: attach notes to commits without changing them
- [ ] `git replace`: temporarily substitute one object for another

### Git Migration / Patch Workflows

- [ ] `git-cvsimport`: import from CVS
- [ ] `git-cvsserver`: CVS server emulator backed by Git
- [ ] `git-svn`: bidirectional Subversion/Git bridge
- [ ] `git-p4`: import from and submit to Perforce repositories
- [ ] `git-quiltimport`: apply a quilt patchset onto the current branch
- [ ] `git-imap-send`: send patches from stdin to an IMAP folder
- [ ] `git-request-pull`: generate a summary of pending changes for maintainers
- [ ] `git-send-email`: send patches as email

### Git Low-Level / Plumbing

- [ ] `git-apply`: apply a patch to files and/or the index
- [ ] `git-checkout-index`: copy files from the index to the working tree
- [ ] `git-commit-graph`: write/verify commit-graph files
- [ ] `git-commit-tree`: create a commit object directly
- [ ] `git-hash-object`: compute or write object IDs from files
- [ ] `git-index-pack`: build an index for a pack file
- [ ] `git-merge-file`: run a three-way file merge
- [ ] `git-merge-index`: run a merge for files needing merging
- [ ] `git-mktag`: create a tag object with extra validation
- [ ] `git-mktree`: build a tree object from `ls-tree` formatted text
- [ ] `git-multi-pack-index`: write/verify multi-pack-indexes
- [ ] `git-pack-objects`: create a packed archive of objects
- [ ] `git-prune-packed`: remove loose objects already present in pack files
- [ ] `git-read-tree`: read tree information into the index
- [ ] `git-replay`: experimental commit replay on a new base
- [ ] `git-symbolic-ref`: read/modify/delete symbolic refs
- [ ] `git-unpack-objects`: unpack objects from a packed archive
- [ ] `git-update-ref`: safely update refs
- [ ] `git-write-tree`: create a tree object from the current index

### Git Interrogation / Debugging

- [ ] `git-cherry`: find commits not yet applied upstream
- [ ] `git-diff-files`: compare working tree files with the index
- [ ] `git-diff-index`: compare a tree with the working tree or index
- [ ] `git-diff-tree`: compare blobs found via tree objects
- [ ] `git-for-each-repo`: run a Git command across multiple repositories
- [ ] `git-ls-remote`: list refs in a remote repository
- [ ] `git-merge-base`: find a good common ancestor for a merge
- [ ] `git-name-rev`: find symbolic names for given revisions
- [ ] `git-show-ref`: list refs in a local repository
- [ ] `git-var`: show Git logical variables
- [ ] `git-verify-pack`: validate packed Git archive files

### Git Internal Helpers

- [ ] `git-check-attr`: display `gitattributes` information
- [ ] `git-check-ignore`: debug `gitignore` / exclude rules
- [ ] `git-check-mailmap`: show canonical names/emails from mailmap data
- [ ] `git-check-ref-format`: check whether a ref name is valid
- [ ] `git-column`: display data in columns
- [ ] `git-credential-cache`: temporarily cache credentials in memory
- [ ] `git-credential-store`: store credentials on disk
- [ ] `git-fmt-merge-msg`: produce a merge commit message
- [ ] `git-hook`: run Git hooks
- [ ] `git-interpret-trailers`: parse/add structured commit-message trailers
- [ ] `git-mailinfo`: extract patch and authorship from an email
- [ ] `git-mailsplit`: split mbox input into messages
- [ ] `git-patch-id`: compute stable patch IDs
- [ ] `git-stripspace`: remove unnecessary whitespace

## Storage / Filesystems

### Partitioning / Block Devices

- [ ] `cfdisk`: friendlier TUI partition editor
- [ ] `sfdisk`: scriptable partition table tool
- [ ] `partprobe`: ask the kernel to re-read partition tables
- [ ] `partx`: add/remove partition mappings from the kernel
- [ ] `addpart`: tell the kernel about a partition
- [ ] `delpart`: tell the kernel to forget a partition
- [ ] `parted`: partition editor, especially for GPT workflows
- [ ] `resizepart`: resize a partition entry without recreating it
- [ ] `blockdev`: inspect/set block device parameters
- [ ] `wipefs`: clear filesystem signatures before repurposing disks
- [ ] `blkdiscard`: TRIM/discard entire block device
- [ ] `fstrim`: periodic TRIM for SSDs
- [ ] `losetup`: loop device management
- [ ] `kpartx`: create device maps from partition tables
- [ ] `zramctl`: inspect/configure compressed RAM block devices

### Filesystem Repair / Metadata

- [ ] `tune2fs`: inspect/tune ext filesystems
- [ ] `debugfs`: low-level ext filesystem inspection
- [ ] `xfs_db`: inspect/debug XFS metadata
- [ ] `xfs_io`: inspect/test XFS and generic filesystem I/O
- [ ] `xfs_growfs`: grow XFS filesystem
- [ ] `xfs_repair`: repair XFS
- [ ] `xfs_info`: XFS filesystem info
- [ ] `e2fsck`: ext filesystem check
- [ ] `dumpe2fs`: ext filesystem info
- [ ] `badblocks`: scan for bad blocks
- [ ] `dosfsck`: check/repair FAT filesystems
- [ ] `dosfslabel`: read/set FAT filesystem label
- [ ] `e2freefrag`: report ext filesystem free-space fragmentation
- [ ] `e2image`: save critical ext filesystem metadata
- [ ] `e2label`: read/set ext filesystem label
- [ ] `e2mmpstatus`: check ext4 MMP status
- [ ] `e2undo`: replay an ext filesystem undo log
- [ ] `e4crypt`: ext4 encryption helper
- [ ] `e4defrag`: defragment ext4 filesystems
- [ ] `filefrag`: report file fragmentation
- [ ] `fsfreeze`: suspend/resume filesystem writes

### Filesystem Creation / Mounting

- [ ] `mkfs`: create filesystems
- [ ] `mkfs.exfat`: create exFAT filesystems
- [ ] `mkfs.f2fs`: create F2FS filesystems
- [ ] `mkfs.vfat`: create FAT/VFAT filesystems
- [ ] `resize2fs`: resize ext **filesystems**
- [ ] `dump.exfat`: inspect exFAT on-disk metadata
- [ ] `tune.exfat`: tune exFAT filesystem metadata
- [ ] `mkswap`: initialise swap space
- [ ] `swaplabel`: read/set swap area label/UUID
- [ ] `ntfs-3g`: mount NTFS read/write in userspace
- [ ] `ntfsclone`: clone NTFS filesystems efficiently
- [ ] `ntfsfix`: fix common NTFS problems / schedule Windows check
- [ ] `ntfsinfo`: inspect NTFS metadata
- [ ] `ntfslabel`: read/set NTFS label
- [ ] `ntfsls`: list NTFS filesystem contents
- [ ] `ntfsresize`: resize NTFS filesystems
- [ ] `ntfsundelete`: recover deleted files from NTFS

### LVM / RAID / Device Mapper

- [ ] `mdadm`: software RAID management
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
- [ ] `dmsetup`: low-level device-mapper management
- [ ] `dmstats`: device-mapper statistics
- [ ] `cache_check`: validate device-mapper cache metadata
- [ ] `cache_dump`: dump device-mapper cache metadata
- [ ] `cache_repair`: repair device-mapper cache metadata
- [ ] `thin_check`: validate thin-provisioning metadata
- [ ] `thin_dump`: dump thin-provisioning metadata
- [ ] `thin_ls`: list thin-provisioned volumes/snapshots
- [ ] `thin_repair`: repair thin-provisioning metadata
- [ ] `thin_restore`: restore thin-provisioning metadata

### Btrfs / ZFS

- [ ] `btrfs`: btrfs management
- [ ] `btrfsck`: legacy alias/wrapper for Btrfs check/repair
- [ ] `btrfs-convert`: convert ext filesystems to Btrfs in place
- [ ] `btrfs-find-root`: find Btrfs roots after damage
- [ ] `btrfs-image`: create/restore Btrfs metadata images
- [ ] `btrfs-map-logical`: map Btrfs logical extents to physical locations
- [ ] `btrfs-select-super`: recover by selecting a Btrfs backup superblock
- [ ] `btrfstune`: tune Btrfs filesystem parameters
- [ ] `compsize`: calculate compression ratio for Btrfs files
- [ ] `zpool`: manage ZFS pools
- [ ] `zfs`: manage ZFS datasets, snapshots, properties, and sends/receives
- [ ] `zdb`: low-level ZFS debugging and metadata inspection

### Quotas / Attributes / FUSE

- [ ] `chattr`: change Linux extended file attributes
- [ ] `getfattr`: read extended file attributes
- [ ] `setfattr`: set extended file attributes
- [ ] `xfs_quota`: manage XFS
- [ ] `quota`: show quotas
- [ ] `quotacheck`: scan filesystem for quotas
- [ ] `quotaon`: enable quotas
- [ ] `quotaoff`: disable quotas
- [ ] `edquota`: edit user quotas
- [ ] `repquota`: quota report
- [ ] `setquota`: set quota non-interactively
- [ ] `fuse-overlayfs`: userspace overlay filesystem, common for rootless containers
- [ ] `fuse2fs`: mount ext filesystems through FUSE
- [ ] `fusermount`: unmount FUSE filesystems
- [ ] `fusermount3`: unmount FUSE3 filesystems
- [ ] `mount.fuse`: mount FUSE filesystems
- [ ] `mount.fuse3`: mount FUSE3 filesystems

### Remote Block Storage

- [ ] `iscsiadm`: manage iSCSI discovery, login, and sessions
- [ ] `nbdinfo`: inspect Network Block Device exports
- [ ] `nbdcopy`: copy data to/from Network Block Device exports
- [ ] `nbdkit`: serve disk images/data as Network Block Devices

## Kernel / Hardware / Boot

### Kernel Modules / Device Events

- [ ] `udevadm`: inspect devices and udev events/rules
- [ ] `lsmod`: list loaded kernel modules
- [ ] `modprobe`: load/unload kernel modules with dependency handling
- [ ] `modinfo`: inspect kernel module metadata
- [ ] `rmmod`: remove a loaded kernel module directly
- [ ] `insmod`: insert a kernel module directly
- [ ] `depmod`: generate module dependency metadata

### Hardware Diagnostics

- [ ] `dmidecode`: hardware inventory from BIOS tables
- [ ] `sensors`: read hardware sensor data
- [ ] `lshw`: detailed hardware listing
- [ ] `lspci`: PCI devices (GPUs, NICs, storage controllers)
- [ ] `lsusb`: USB devices
- [ ] `lsscsi`: list SCSI/SATA/SAS devices
- [ ] `nvme`: inspect/manage NVMe devices
- [ ] `hdparm`: disk parameters and benchmarks
- [ ] `lsgpu`: list GPU devices
- [ ] `usb-devices`: detailed USB device listing
- [ ] `udisksctl`: manage disks through UDisks from the CLI

### CPU / Power / Firmware

- [ ] `powertop`: power usage diagnosis and tuning
- [ ] `turbostat`: CPU frequency, C-state, and power diagnostics
- [ ] `hwclock`: inspect/set hardware clock
- [ ] `choom`: inspect/adjust OOM killer score
- [ ] `cpupower`: inspect/tune CPU power management
- [ ] `chcpu`: configure CPUs online/offline
- [ ] `chmem`: configure memory online/offline
- [ ] `wdctl`: inspect watchdog devices
- [ ] `upower`: inspect battery/power devices
- [ ] `fwupdmgr`: firmware updates via fwupd
- [ ] `fwupdtool`: lower-level fwupd tool
- [ ] `boltctl`: manage Thunderbolt devices

### Console / Local Devices

- [ ] `ctrlaltdel`: configure Ctrl-Alt-Del behaviour
- [ ] `kbd_mode`: inspect/set keyboard mode
- [ ] `chvt`: switch virtual terminals
- [ ] `deallocvt`: deallocate unused virtual terminals
- [ ] `dumpkeys`: dump keyboard translation tables
- [ ] `showkey`: show keycodes/scancodes
- [ ] `setfont`: load console font
- [ ] `setterm`: set terminal attributes
- [ ] `showconsolefont`: show current console font glyphs
- [ ] `lsipc`: list System V IPC facilities
- [ ] `lsirq`: list IRQ information
- [ ] `lslocks`: list file locks
- [ ] `lslogins`: inspect user/login metadata

### Boot / Initramfs / Firmware

- [ ] `bootctl`: systemd-boot management, where relevant
- [ ] `grubby`: manage default kernel/boot args on Fedora/RHEL
- [ ] `grub2-mkconfig`: regenerate GRUB configuration
- [ ] `grub2-install`: install GRUB bootloader
- [ ] `dracut`: build initramfs
- [ ] `lsinitrd`: inspect initramfs
- [ ] `efibootmgr`: UEFI boot entries

### Bluetooth / Mobile

- [ ] `adb`: Android Debug Bridge
- [ ] `bluetoothctl`: Bluetooth control shell
- [ ] `btmgmt`: lower-level Bluetooth management shell
- [ ] `btmon`: Bluetooth packet/event monitor
- [ ] `btattach`: attach serial Bluetooth controllers

## Networking / Services

### Diagnostics / Resolver

- [ ] `arping`: ARP-level ping — find IP conflicts on L2
- [ ] `ethtool`: NIC stats, driver info, link detection
- [ ] `clockdiff`: measure clock difference between hosts
- [ ] `delv`: DNS lookup with DNSSEC validation
- [ ] `doggo`: friendly DNS lookup tool
- [ ] `getent`: query NSS databases, especially hosts/address resolution
- [ ] `resolvectl`: inspect/query systemd-resolved
- [ ] `dhcpcd`: DHCP client
- [ ] `dnsdomainname`: show DNS domain name
- [ ] `dnsmasq`: lightweight DNS/DHCP server
- [ ] `dnstap-read`: read dnstap DNS logs
- [ ] `ipmaddr`: inspect multicast addresses; mostly legacy
- [ ] `mii-tool`: inspect old Ethernet link state; mostly superseded by `ethtool`
- [ ] `mmcli`: ModemManager CLI
- [ ] `nmcli`: NetworkManager CLI
- [ ] `netstat`: legacy network/socket tool; prefer `ss` and `ip`
- [ ] `nstat`: network statistics counters
- [ ] `oping`: send ICMP echo requests with richer output
- [ ] `resolvconf`: manage resolver configuration on systems that use it
- [ ] `route`: legacy routing table tool; prefer `ip route`
- [ ] `networkctl`: inspect systemd-networkd link state
- [ ] `nsupdate`: dynamic DNS update client
- [ ] `tcptraceroute`: traceroute over TCP instead of ICMP/UDP

### Low-Level Network Plumbing

- [ ] `arp`: inspect/manipulate ARP cache; mostly legacy beside `ip neigh`
- [ ] `arpaname`: convert IP addresses to reverse-DNS ARPA names
- [ ] `bridge`: bridge management
- [ ] `tc`: traffic control (QoS)
- [ ] `dcb`: data centre bridging
- [ ] `devlink`: devlink device management
- [ ] `rdma`: RDMA management
- [ ] `vdpa`: vDPA management
- [ ] `tipc`: TIPC protocol
- [ ] `teamdctl`: inspect/control network team devices

### Firewall / Packet Filtering

- [ ] `arptables-save`: dump **ARP**** filtering rules
- [ ] `arptables-restore`: restore ARP filtering rules
- [ ] `arptables-translate`: translate ARP rules to nftables form
- [ ] `arptables`: ARP table filtering
- [ ] `ebtables`: ethernet bridge filtering
- [ ] `iptables`: legacy packet filtering
- [ ] `iptables-save`: dump rules
- [ ] `iptables-restore`: load rules
- [ ] `ip6tables`: same for IPv6
- [ ] `iptables-nft`: iptables syntax over nftables backend
- [ ] `ipset`: IP sets for efficient rule matching
- [ ] `iptables-nft-save`: save nft-backed iptables rules
- [ ] `iptables-nft-restore`: restore nft-backed iptables rules
- [ ] `iptables-translate`: translate iptables rules to nftables syntax
- [ ] `ip6tables-save`: save IPv6 iptables rules
- [ ] `ip6tables-restore`: restore IPv6 iptables rules
- [ ] `nft`: nftables packet filtering
- [ ] `fail2ban-client`: inspect/control Fail2ban jails and bans

### HTTP / Services

- [ ] `ab`: ApacheBench HTTP benchmarking
- [ ] `caddy`: Caddy web server CLI and config validation
- [ ] `certbot`: ACME/Let's Encrypt certificate automation
- [ ] `grpcurl`: inspect and invoke gRPC APIs from the CLI
- [ ] `hurl`: run HTTP requests with assertions for API smoke tests
- [ ] `http`: HTTPie command-line HTTP client
- [ ] `oha`: modern HTTP load testing
- [ ] `websocat`: WebSocket client/server for shell pipelines and debugging
- [ ] `GET`: simple command-line HTTP GET client from libwww-perl
- [ ] `HEAD`: simple command-line HTTP HEAD client from libwww-perl
- [ ] `POST`: simple command-line HTTP POST client from libwww-perl
- [ ] `apachectl`: control Apache/httpd

### File Sharing / Network Filesystems

- [ ] `mount.nfs`: NFS mount
- [ ] `mount.nfs4`: NFSv4 mount
- [ ] `nfsstat`: NFS statistics
- [ ] `showmount`: list NFS exports
- [ ] `exportfs`: manage NFS exports
- [ ] `rpcinfo`: RPC service info
- [ ] `rpcclient`: Samba/MS-RPC client for Windows/Samba diagnostics
- [ ] `smbclient`: SMB file access
- [ ] `smbget`: wget-like SMB downloader
- [ ] `smbstatus`: inspect Samba sessions/locks
- [ ] `smbtree`: browse SMB workgroups/shares
- [ ] `mount.cifs`: mount SMB shares
- [ ] `cifscreds`: manage CIFS credentials
- [ ] `smbcacls`: SMB ACLs

### Wireless / VPN / Local Discovery

- [ ] `avahi-daemon`: mDNS/DNS-SD daemon
- [ ] `avahi-browse`: browse mDNS services
- [ ] `avahi-resolve`: resolve mDNS names
- [ ] `iw`: wireless config
- [ ] `wpa_cli`: WPA supplicant control
- [ ] `wpa_supplicant`: WPA auth daemon
- [ ] `nm-online`: wait for network
- [ ] `rfkill`: enable/disable radios
- [ ] `wpa_passphrase`: generate WPA/WPA2 PSK config blocks
- [ ] `mosh`: roaming remote shell for flaky/high-latency connections
- [ ] `openconnect`: VPN client
- [ ] `openvpn`: OpenVPN client/server
- [ ] `vpnc`: Cisco-compatible VPN client

## Systemd / System Administration

### Systemd Tools

- [ ] `loginctl`: session management
- [ ] `localectl`: locale settings
- [ ] `coredumpctl`: manage core dumps
- [ ] `service`: legacy service wrapper; useful on mixed distros
- [ ] `systemd-delta`: compare local unit overrides against vendor units
- [ ] `systemd-analyze`: boot performance analysis
- [ ] `systemd-cgls`: cgroup tree
- [ ] `systemd-cgtop`: cgroup resource usage
- [ ] `systemd-run`: transient units
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
- [ ] `systemd-nspawn`: lightweight container
- [ ] `kernel-install`: install/remove kernel images using systemd conventions
- [ ] `machinectl`: manage containers/VMs (systemd-nspawn)
- [ ] `portablectl`: portable services
- [ ] `homectl`: systemd-homed user management
- [ ] `importctl`: import VM/container images
- [ ] `systemd-firstboot`: initialise basic settings on a new image
- [ ] `systemd-inhibit`: run a command while blocking sleep/shutdown
- [ ] `systemd-notify`: send readiness/status notifications from services
- [ ] `systemd-path`: inspect systemd/user path locations
- [ ] `systemd-socket-activate`: test socket-activated services
- [ ] `systemd-tty-ask-password-agent`: handle systemd password prompts
- [ ] `systemd-umount`: unmount through systemd
- [ ] `userdbctl`: inspect systemd user/group records
- [ ] `varlinkctl`: inspect/call Varlink services

### Shutdown / Rescue / Time

- [ ] `chronyc`: NTP client management
- [ ] `sulogin`: single-user/rescue login shell

### Accounts / Auth / Admin

- [x] `capsh`: inspect Linux capabilities
- [ ] `pkexec`: run GUI/CLI programs via polkit authorisation
- [ ] `chage`: password ageing
- [ ] `chfn`: change a user's GECOS/full-name information
- [ ] `chpasswd`: update passwords in batch
- [ ] `chgpasswd`: update group passwords in batch
- [ ] `cvtsudoers`: convert sudoers files between formats
- [ ] `authselect`: select/manage Fedora/RHEL authentication profiles
- [ ] `realm`: join/manage identity domains such as AD/FreeIPA
- [ ] `sss_cache`: clear SSSD cached identity/auth data
- [ ] `groupmems`: manage supplementary group membership
- [ ] `pwck`: check passwd/shadow file integrity
- [ ] `grpck`: check group/gshadow file integrity
- [ ] `newuidmap`: set UID mappings for user namespaces
- [ ] `newgidmap`: set GID mappings for user namespaces
- [ ] `run0`: systemd's sudo-like privilege escalation tool

### Package / Distro Maintenance

- [ ] `apt-file`: find which Debian/Ubuntu package provides a file
- [ ] `needrestart`: report services/processes needing restart after package upgrades
- [ ] `dnf5`: DNF5 package manager frontend
- [ ] `dnf4`: older DNF4 frontend where installed separately
- [ ] `dnf-automatic`: automatic DNF update service/config tool
- [ ] `microdnf`: minimal DNF frontend used in small images
- [ ] `rpm2cpio`: extract payloads from RPM packages
- [ ] `rpmconf`: manage `.rpmnew`/`.rpmsave` config merges
- [ ] `rpmkeys`: verify/import RPM package keys
- [ ] `rpmdb`: inspect/rebuild RPM database
- [ ] `rpmsort`: sort RPM version strings
- [ ] `applydeltarpm`: reconstruct RPMs from delta RPMs
- [ ] `appstreamcli`: query/validate AppStream metadata

### Desktop / Fedora Plumbing

- [ ] `xdg-mime`: inspect/set MIME associations
- [ ] `busctl`: inspect and call D-Bus services
- [ ] `gdbus`: D-Bus inspection/calling from GLib tooling
- [ ] `dbus-monitor`: watch D-Bus messages
- [ ] `sos`: collect RHEL/Fedora diagnostic bundles
- [ ] `wall`: broadcast a message to logged-in users
- [ ] `write`: send a message to another logged-in user's terminal

## Security / Crypto / Policy

### Certificates / PKCS / Smartcards

- [ ] `certtool`: GnuTLS cert tool
- [ ] `mkcert`: create locally trusted development certificates
- [ ] `step`: Smallstep CLI for certificates, ACME, and internal PKI workflows
- [ ] `p11-kit`: PKCS#11 module management
- [ ] `pkcs11-tool`: inspect and use PKCS#11 tokens/smartcards
- [ ] `openpgp-tool`: inspect/use OpenPGP smartcards
- [ ] `opensc-tool`: inspect smartcards through OpenSC
- [ ] `p11tool`: GnuTLS PKCS#11 tool
- [ ] `pkcs15-tool`: inspect/use PKCS#15 smartcards
- [ ] `cardos-tool`: inspect CardOS smartcards
- [ ] `danetool`: GnuTLS DANE helper

### GPG / Crypto / Passwords

- [ ] `keychain`: manage long-lived `ssh-agent`/`gpg-agent` sessions
- [ ] `gpg-agent`: GnuPG private-key agent
- [ ] `gpgconf`: inspect/configure GnuPG components
- [ ] `gpg-connect-agent`: talk directly to `gpg-agent`
- [ ] `gpgv`: verify OpenPGP signatures only
- [ ] `keyctl`: manage Linux kernel keyrings
- [ ] `pinentry`: password/PIN prompt used by GnuPG
- [ ] `unshadow`: combine passwd/shadow for password audit tools
- [ ] `cracklib-check`: check password strength against cracklib

### Secrets / Policy

- [ ] `vault`: HashiCorp Vault CLI for secrets and identity workflows
- [ ] `opa`: Open Policy Agent policy evaluation
- [ ] `conftest`: test config and IaC files with OPA policies

### Secure Boot / Disk Unlocking / Crypto Policy

- [ ] `dbxtool`: manage UEFI dbx revocation data
- [ ] `mokutil`: inspect/manage Secure Boot MOK keys
- [ ] `update-crypto-policies`: inspect/set Fedora/RHEL system crypto policy
- [ ] `clevis`: policy-based decryption framework
- [ ] `clevis-luks-bind`: bind LUKS unlocking to TPM2/Tang/SSS policy
- [ ] `clevis-luks-list`: list Clevis bindings on a LUKS device
- [ ] `clevis-luks-unbind`: remove Clevis bindings
- [ ] `clevis-luks-unlock`: unlock a Clevis-bound LUKS device

### SELinux

- [ ] `semanage`: manage SELinux policy
- [ ] `chcon`: change file context
- [ ] `setsebool`: set SELinux booleans
- [ ] `getsebool`: get SELinux booleans
- [ ] `audit2allow`: generate policy from denials
- [ ] `semodule`: manage SELinux modules
- [ ] `matchpathcon`: check expected context for path
- [ ] `runcon`: run a command with a chosen SELinux context
- [ ] `avcstat`: show SELinux AVC statistics
- [ ] `chcat`: change SELinux security categories
- [ ] `checkmodule`: compile SELinux policy modules
- [ ] `checkpolicy`: compile SELinux policy
- [ ] `secon`: show SELinux context information
- [ ] `selinuxenabled`: test whether SELinux is enabled
- [ ] `setfiles`: set SELinux file contexts from policy

### Audit / Accounting

- [ ] `auditctl`: audit rule management
- [ ] `aureport`: audit reports
- [ ] `ausearch`: search audit logs
- [ ] `augenrules`: generate audit rules from files
- [ ] `ac`: show user connection-time accounting
- [ ] `accton`: enable/disable process accounting
- [ ] `lastcomm`: show previously executed commands from process accounting
- [ ] `sa`: summarise process accounting records
- [ ] `dump-acct`: print process accounting files in human-readable form
- [ ] `dump-utmp`: print utmp login/session records
- [ ] `aulast`: audit-log equivalent of `last`
- [ ] `aulastlog`: audit-log equivalent of `lastlog`
- [ ] `ausyscall`: map syscall names and numbers

## Containers / Virtualisation / Kubernetes

### Container Internals

- [ ] `crictl`: inspect/debug CRI container runtimes
- [ ] `ctr`: containerd CLI
- [ ] `crun`: container runtime (low-level)
- [ ] `conmon`: container monitor (low-level)
- [ ] `lsns`: inspect Linux namespaces
- [ ] `nsenter`: enter container/process namespaces for debugging
- [ ] `unshare`: create a fresh namespace view for testing/isolation
- [ ] `buildah`: build OCI images
- [ ] `journalctl -u container-*`: if using podman/systemd units
- [ ] `bwrap`: Bubblewrap sandbox/container setup utility
- [ ] `criu`: checkpoint/restore in userspace

### Container Build / Registry / Supply Chain

- [ ] `crane`: inspect, copy, and delete container images in registries without Docker
- [ ] `oras`: push and pull generic OCI registry artifacts
- [ ] `hadolint`: lint Dockerfiles
- [ ] `dive`: inspect container image layers and wasted space
- [ ] `syft`: generate SBOMs for container images and filesystems
- [ ] `grype`: scan images and filesystems for vulnerabilities

### Kubernetes

- [ ] Kubernetes model: pods, deployments, services, ingress, secrets, volumes
- [ ] `kind`: local Kubernetes clusters in Docker/Podman containers
- [ ] `minikube`: local Kubernetes cluster manager
- [ ] `kubectx`: switch Kubernetes contexts quickly
- [ ] `kubens`: switch Kubernetes namespaces quickly
- [ ] `kubectl`: Kubernetes CLI
- [ ] `krew`: kubectl plugin manager
- [ ] `helm`: Kubernetes package manager
- [ ] `helmfile`: manage groups of Helm releases declaratively
- [ ] `k9s`: Kubernetes TUI
- [ ] `stern`: tail logs from multiple pods
- [ ] `kustomize`: patch and compose Kubernetes manifests
- [ ] `argocd`: Argo CD CLI for GitOps deployments
- [ ] `flux`: Flux GitOps CLI
- [ ] `velero`: Kubernetes backup and restore
- [ ] `kubeseal`: encrypt Kubernetes Secrets for Sealed Secrets

### Proxmox

- [ ] `qm`: Proxmox QEMU/KVM VM management
- [ ] `pct`: Proxmox LXC container management
- [ ] `pvesh`: Proxmox API shell
- [ ] `pvecm`: Proxmox cluster management
- [ ] `pveam`: Proxmox appliance/template manager
- [ ] `vzdump`: Proxmox backup tool
- [ ] `proxmox-backup-client`: Proxmox Backup Server client

### Libvirt / QEMU

- [ ] `virsh`: libvirt CLI — VM management
- [ ] `virt-install`: create VMs
- [ ] `virt-clone`: clone VMs
- [ ] `virt-manager`: GUI VM manager
- [ ] `virt-admin`: administer libvirt daemons
- [ ] `virt-qemu-run`: run VM images directly through libvirt/QEMU tooling
- [ ] `virt-ssh-helper`: helper for SSH access via libvirt
- [ ] `virt-viewer`: view VM graphical consoles
- [ ] `virt-xml`: edit libvirt XML safely-ish from CLI
- [ ] `virt-xml-validate`: validate libvirt XML
- [ ] `qemu-img`: disk image creation/conversion
- [ ] `qemu-kvm`: KVM hypervisor
- [ ] `qemu-system-x86_64`: full system emulator
- [ ] `qemu-io`: test/debug QEMU disk images
- [ ] `qemu-system-i386`: run 32-bit x86 system emulation
- [ ] `qemu-nbd`: expose QEMU disk images as network block devices
- [ ] `qemu-ga`: QEMU guest agent
- [ ] `virt-what`: detect whether the system is running inside a VM
- [ ] `virt-host-validate`: validate host setup for libvirt/KVM

### VM Disk Inspection

- [ ] `guestfish`: inspect/edit VM disk images via libguestfs
- [ ] `virt-cat`: read files from VM disk images
- [ ] `virt-ls`: list files in VM disk images
- [ ] `virt-edit`: edit files inside VM disk images
- [ ] `virt-df`: show disk usage for VM images
- [ ] `virt-sysprep`: prepare/clean VM images for cloning

## Cloud / Infrastructure / IaC

### Cloud CLIs

- [ ] `gcloud`: Google Cloud CLI
- [ ] `az`: Azure CLI

### Terraform / Image Build

- [ ] `tofu`: OpenTofu, Terraform-compatible IaC workflow
- [ ] `tofu-ls`: OpenTofu/Terraform language server
- [ ] `packer`: build AMIs and other machine images
- [ ] `terragrunt`: wrapper/orchestration for Terraform and OpenTofu estates
- [ ] `checkov`: IaC security scanning

### Infrastructure Debugging

- [ ] `mpstat`: per-CPU usage and steal time (sysstat)
- [ ] `sar`: historical system activity from sysstat
- [ ] `lsfd`: modern file descriptor/socket inspection
- [ ] `inotifywait`: watch file changes/events for automation and debugging

### Monitoring / Observability

- [ ] `promtool`: validate Prometheus config and alerting rules

### Backup / Recovery

- [ ] `kopia`: modern encrypted/deduplicated backup tool
- [ ] `rear`: Relax-and-Recover — bare metal DR

## Dev / Build / Languages

### Repo Hygiene / CI / Static Analysis

- [ ] `semgrep`: static analysis and security scanning with code-aware patterns

### Language / Dev Tooling

- [ ] `npx`: run Node package binaries without permanent install
- [ ] `yarn`: alternative Node package manager
- [ ] `mise`: manage language/tool versions per project
- [ ] `asdf`: language/runtime version manager
- [ ] `devbox`: reproducible development shells built on Nix
- [ ] `nix`: package manager and reproducible build/dev environment toolkit
- [ ] `uv`: fast Python package/project tool
- [ ] `ruff`: fast Python linter/formatter
- [ ] `pytest`: Python test runner
- [ ] `tox`: Python test environment matrix automation
- [ ] `nox`: Python automation and test sessions
- [ ] `cargo`: Rust package/build tool
- [ ] `rustc`: Rust compiler
- [ ] `java`: JVM launcher
- [ ] `zig`: Zig compiler/toolchain
- [ ] `go`: Go toolchain
- [ ] `perldoc`: read Perl documentation
- [ ] `cpan`: install/query Perl modules from CPAN
- [ ] `corelist`: query which Perl modules shipped with which Perl versions
- [ ] `pip3`: Python package installer alias
- [ ] `pydoc3`: Python documentation browser
- [ ] `python3-config`: Python build flags for compiling extensions
- [ ] `idle3`: Python's basic GUI IDE
- [ ] `luajit`: LuaJIT interpreter

### Build Systems / Toolchains

- [ ] `ccache`: compiler cache for repeated C/C++ builds
- [ ] `sccache`: compiler cache for Rust/C/C++ builds
- [ ] `gcc`: C compiler
- [ ] `cmake`: generate native build files for C/C++ projects
- [ ] `ninja`: fast build backend, often generated by CMake or Meson
- [ ] `pkg-config`: compiler/linker flags for libraries
- [ ] `autoconf`: generate configure scripts
- [ ] `autoheader`: generate configure header templates
- [ ] `automake`: generate Makefile.in files
- [ ] `autoreconf`: regenerate an autotools build system
- [ ] `autoscan`: scan source tree for configure.ac hints
- [ ] `autoupdate`: update old autoconf input files
- [ ] `m4`: macro processor used by autotools and other build systems
- [ ] `libtool`: portable library build helper
- [ ] `libtoolize`: add libtool support files to a project
- [ ] `bison`: parser generator
- [ ] `flex`: lexer generator
- [ ] `c89`: compile in C89 mode
- [ ] `c99`: compile in C99 mode
- [ ] `cc`: system C compiler frontend
- [ ] `c++`: system C++ compiler frontend
- [ ] `g++`: GNU C++ compiler
- [ ] `cpp`: C preprocessor
- [ ] `gettext`: translate strings / inspect gettext tooling
- [ ] `gettextize`: add gettext infrastructure to a source tree
- [ ] `msgfmt`: compile gettext `.po` files
- [ ] `msgmerge`: merge gettext translations with updated templates
- [ ] `gmake`: GNU make command name on systems where `make` may differ
- [ ] `pkgconf`: `pkg-config` compatible implementation
- [ ] `yasm`: assembler
- [ ] `check-regexp`: test regular expressions from the command line
- [ ] `doxygen`: generate API documentation from source

### Binary / Debug Internals

- [ ] `ldd`: show shared library dependencies
- [ ] `ldconfig`: configure dynamic linker cache
- [ ] `gdb`: native debugger for C/C++ and low-level process inspection
- [ ] `readelf`: inspect ELF binaries and shared libraries
- [ ] `objdump`: disassemble and inspect object files/binaries
- [ ] `nm`: list symbols from object files and binaries
- [ ] `addr2line`: map program addresses back to source locations
- [ ] `strip`: remove symbols/debug info from binaries
- [ ] `ar`: create and inspect static library archives
- [ ] `gcov`: GCC coverage reporting
- [ ] `c++filt`: demangle C++ symbols
- [ ] `objcopy`: copy/transform object files and binary sections
- [ ] `dwz`: optimise DWARF debug info
- [ ] `debuginfod-find`: fetch debug info/source files from debuginfod servers
- [ ] `dtrace`: user-space static probe generation / tracing frontend

## Documents / Data / Media

### PDFs / Documents

- [ ] `pdfinfo`: inspect PDF metadata/page info
- [ ] `qpdf`: inspect, repair, split, merge, and transform PDFs
- [ ] `exiftool`: inspect/edit metadata on documents, images, and media
- [ ] `pdfimages`: extract images from PDFs
- [ ] `pdfunite`: concatenate PDFs
- [ ] `soffice`: LibreOffice CLI for document conversion/printing
- [ ] `libreoffice`: LibreOffice CLI alias/front door
- [ ] `gs`: Ghostscript CLI for PostScript/PDF processing
- [ ] `pdftocairo`: convert PDF pages to images/vector formats
- [ ] `pdftoppm`: convert PDF pages to bitmap images
- [ ] `antiword`: extract text from old `.doc` files
- [ ] `ebook-convert`: convert ebook formats via Calibre
- [ ] `ps2pdf`: convert PostScript to PDF
- [ ] `pdfattach`: attach files to PDFs
- [ ] `pdfdetach`: extract PDF attachments
- [ ] `pdffonts`: list fonts used by a PDF
- [ ] `pdfseparate`: split PDF pages into separate files
- [ ] `pdfsig`: inspect/verify PDF signatures
- [ ] `pdftohtml`: convert PDF to HTML
- [ ] `pdftops`: convert PDF to PostScript

### Structured Text / Data Formats

- [ ] `dasel`: query and edit JSON, YAML, TOML, XML, and CSV
- [ ] `htmlq`: extract HTML with CSS selectors
- [ ] `iconv`: character encoding conversion
- [ ] `duckdb`: local analytical SQL over CSV, Parquet, JSON, and databases
- [ ] `mlr`: Miller data wrangling for CSV, TSV, JSON, and tables
- [ ] `qsv`: fast CSV slicing, filtering, stats, and validation
- [ ] `sqlite-utils`: inspect, transform, and import data into SQLite databases
- [ ] `visidata`: terminal spreadsheet/data explorer
- [ ] `xmlstarlet`: query and edit XML from the CLI
- [ ] `xmllint`: validate, format, and query XML
- [ ] `xsltproc`: apply XSLT transforms to XML
- [ ] `recode-sr-latin`: Serbian Latin recoding helper
- [ ] `chardetect`: detect text encoding
- [ ] `uchardet`: detect character encoding
- [ ] `csv2ods`: convert CSV to OpenDocument spreadsheet
- [ ] `json_pp`: pretty-print JSON
- [ ] `json_verify`: validate JSON
- [ ] `markdown_py`: render Markdown via Python-Markdown
- [ ] `unix2dos`: create Windows line endings

### Images / Audio / Video

- [ ] `identify`: inspect image metadata
- [ ] `mogrify`: batch-modify images in place
- [ ] `ffmpeg`: media conversion, remuxing, extraction, and repair
- [ ] `ffprobe`: inspect media metadata and streams
- [ ] `ffplay`: quick media playback/debugging from FFmpeg
- [ ] `ghostscript`: PostScript/PDF interpreter; usually invoked as `gs`
- [ ] `magick`: ImageMagick entry point for image conversion and manipulation
- [ ] `convert`: legacy ImageMagick conversion command; prefer `magick` on newer systems
- [ ] `compare`: ImageMagick visual/image comparison
- [ ] `display`: ImageMagick image viewer
- [ ] `animate`: ImageMagick image sequence viewer
- [ ] `composite`: ImageMagick image compositing
- [ ] `img2pdf`: images to PDF
- [ ] `tesseract`: OCR engine behind ocrmypdf
- [ ] `cjpeg`: encode JPEG images
- [ ] `djpeg`: decode JPEG images
- [ ] `cwebp`: encode WebP images
- [ ] `dwebp`: decode WebP images
- [ ] `optipng`: optimise PNG files
- [ ] `pngquant`: lossy PNG compression
- [ ] `unpaper`: clean up scanned pages before OCR/PDF assembly
- [ ] `webpinfo`: inspect WebP files
- [ ] `webpmux`: create/extract WebP containers/metadata
- [ ] `cd-info`: inspect CD/CD-image metadata
- [ ] `cd-read`: read data from CD/CD images
- [ ] `cd-paranoia`: robust audio CD ripping
- [ ] `cdrecord`: burn CDs/DVDs/BDs via xorriso compatibility
- [ ] `aconnect`: ALSA sequencer connection manager
- [ ] `amidi`: read/write ALSA RawMIDI ports
- [ ] `aplaymidi`: play MIDI files
- [ ] `arecordmidi`: record MIDI files

### Printing / Scanning

- [ ] `lpadmin`: configure CUPS printers/classes
- [ ] `lpinfo`: show CUPS devices/drivers
- [ ] `lpoptions`: inspect/set printer options
- [ ] `lpq`: inspect print queue
- [ ] `lpr`: BSD-style print command
- [ ] `lprm`: remove print jobs
- [ ] `lpstat`: show CUPS printer/queue status
- [ ] `cancel`: cancel print jobs
- [ ] `scanimage`: command-line scanner frontend
- [ ] `sane-find-scanner`: detect scanners for SANE
- [ ] `airscan-discover`: discover eSCL/AirScan-compatible scanners

### Graphviz / Visualisation

- [ ] `dot`: render Graphviz DOT graphs
- [ ] `neato`: render Graphviz graphs with spring layouts
- [ ] `fdp`: render undirected Graphviz graphs
- [ ] `sfdp`: render large undirected Graphviz graphs
- [ ] `circo`: render circular Graphviz layouts
- [ ] `twopi`: render radial Graphviz layouts
- [ ] `acyclic`: make a directed graph acyclic
- [ ] `bcomps`: find biconnected components in graphs
- [ ] `ccomps`: find connected components in graphs
- [ ] `dijkstra`: Graphviz shortest-path filter
- [ ] `unflatten`: adjust graph aspect ratio before layout
- [ ] `tred`: transitive reduction filter for directed graphs

## Personal / Interactive Apps

- [ ] `screen`: terminal multiplexer, mostly superseded by `tmux`
- [ ] `tmate`: temporary terminal sharing/pairing over SSH
- [ ] `zellij`: modern terminal workspace/multiplexer
- [ ] `btm`: another modern process/resource monitor (`bottom`)
- [ ] `brave-browser`: launch Brave from the shell
- [ ] `calibre`: ebook manager
- [ ] `ebook-viewer`: Calibre ebook viewer
- [ ] `mpv`: media player
- [ ] `nano`: simple terminal editor
- [ ] `qwen`: Qwen CLI/local model tool if you use it
- [ ] `speedtest-cli`: Python speed test CLI
- [ ] `thunderbird`: launch Thunderbird from the shell
- [ ] `xsel`: X11 clipboard tool
- [ ] `zeal`: offline API/doc browser
- [ ] `zoom`: launch Zoom from the shell
