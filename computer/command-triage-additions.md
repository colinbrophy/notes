#ai-written
# Command Triage Additions

Companion note for practical omissions from [[command-triage]]. These are candidates to fold into the main triage later, not a claim that every command deserves equal study.

## Disk / Filesystem Basics

- [ ] `fdisk`: classic disk partition editor
- [ ] `cfdisk`: friendlier TUI partition editor
- [ ] `sfdisk`: scriptable partition table tool
- [ ] `parted`: partition editor, especially for GPT workflows
- [ ] `partprobe`: ask the kernel to re-read partition tables
- [ ] `partx`: add/remove partition mappings from the kernel
- [ ] `mkfs`: create filesystems
- [ ] `fsck`: check/repair filesystems
- [ ] `mkswap`: initialise swap space
- [ ] `tune2fs`: inspect/tune ext filesystems
- [ ] `debugfs`: low-level ext filesystem inspection
- [ ] `xfs_db`: inspect/debug XFS metadata
- [ ] `xfs_io`: inspect/test XFS and generic filesystem I/O
- [ ] `xfs_quota`: manage XFS
- [ ] `xfs_growfs`: grow XFS filesystem
- [ ] `xfs_repair`: repair XFS
- [ ] `xfs_info`: 
- [ ] `e2fsck`: ext filesystem check
- [ ] `dumpe2fs`: ext filesystem infoXFS filesystem info quotas
- [ ] `zramctl`: inspect/configure compressed RAM block devices
- [ ] `snapper`: filesystem snapshot management, especially on Btrfs/openSUSE-style setups

## ZFS / Proxmox

- [ ] `zpool`: manage ZFS pools
- [ ] `zfs`: manage ZFS datasets, snapshots, properties, and sends/receives
- [ ] `zdb`: low-level ZFS debugging and metadata inspection
- [ ] `qm`: Proxmox QEMU/KVM VM management
- [ ] `pct`: Proxmox LXC container management
- [ ] `pvesh`: Proxmox API shell
- [ ] `pvecm`: Proxmox cluster management
- [ ] `pveam`: Proxmox appliance/template manager
- [ ] `vzdump`: Proxmox backup tool
- [ ] `proxmox-backup-client`: Proxmox Backup Server client

## Kernel / Modules / Hardware

- [ ] `lsmod`: list loaded kernel modules
- [ ] `modprobe`: load/unload kernel modules with dependency handling
- [ ] `modinfo`: inspect kernel module metadata
- [ ] `rmmod`: remove a loaded kernel module directly
- [ ] `insmod`: insert a kernel module directly
- [ ] `depmod`: generate module dependency metadata
- [ ] `hwclock`: inspect/set hardware clock
- [ ] `sensors`: read hardware sensor data
- [ ] `powertop`: power usage diagnosis and tuning
- [ ] `turbostat`: CPU frequency, C-state, and power diagnostics

## Core Unix Odds And Ends

- [ ] `sleep`: delay for a fixed duration
- [ ] `which`: locate a command in `PATH`; prefer `type` for shell-aware lookup
- [ ] `mkfifo`: create named pipes
- [ ] `mknod`: create device nodes/FIFOs manually
- [ ] `stdbuf`: adjust stdio buffering in pipelines
- [ ] `sdiff`: side-by-side diff
- [ ] `csplit`: split files by context/pattern
- [ ] `tsort`: topological sort
- [ ] `chattr`: change Linux extended file attributes
- [ ] `lsattr`: list Linux extended file attributes
- [ ] `getfattr`: read extended file attributes
- [ ] `setfattr`: set extended file attributes
- [ ] `setpriv`: run a program with modified Linux privileges
- [ ] `runuser`: run command as another user, often from root scripts
- [ ] `setsid`: run a command in a new session

## Desktop / Fedora Plumbing

- [ ] `nmcli`: NetworkManager CLI; worth promoting from situational to core networking
- [ ] `xdg-open`: open a file/URL with the desktop default app
- [ ] `xdg-mime`: inspect/set MIME associations
- [ ] `gio`: GLib/GVfs file and metadata operations
- [ ] `busctl`: inspect and call D-Bus services
- [ ] `gdbus`: D-Bus inspection/calling from GLib tooling
- [ ] `dbus-monitor`: watch D-Bus messages
- [ ] `secret-tool`: query/store secrets via libsecret
- [ ] `toolbox`: Fedora containerised development environments

## PDF / Document / Media Work

- [ ] `pdftotext`: extract text from PDFs
- [ ] `pdfinfo`: inspect PDF metadata/page info
- [ ] `pdfimages`: extract images from PDFs
- [ ] `pdfunite`: concatenate PDFs
- [ ] `pdfgrep`: grep through PDF text
- [ ] `qpdf`: inspect, repair, split, merge, and transform PDFs
- [ ] `exiftool`: inspect/edit metadata on documents, images, and media
- [ ] `magick`: ImageMagick entry point for image conversion and manipulation
- [ ] `identify`: inspect image metadata
- [ ] `mogrify`: batch-modify images in place
- [ ] `soffice`: LibreOffice CLI for document conversion/printing
- [ ] `libreoffice`: LibreOffice CLI alias/front door

## Compression

- [ ] `zstd`: modern fast compression
- [ ] `zstdcat`: stream decompressed zstd data
- [ ] `zstdgrep`: grep compressed zstd files
- [ ] `zstdless`: page compressed zstd files
- [ ] `lz4`: very fast compression
- [ ] `lz4cat`: stream decompressed lz4 data
- [ ] `xzcat`: stream decompressed xz data
- [ ] `bzcat`: stream decompressed bzip2 data
- [ ] `zipinfo`: inspect zip archive contents/metadata
- [ ] `7z`: handle 7-Zip and many archive formats

## Infra / Kubernetes Extras

- [ ] `tofu`: OpenTofu, Terraform-compatible IaC workflow
- [ ] `tofu-ls`: OpenTofu/Terraform language server
- [ ] `kind`: local Kubernetes clusters in Docker/Podman containers
- [ ] `minikube`: local Kubernetes cluster manager
- [ ] `crictl`: inspect/debug CRI container runtimes
- [ ] `ctr`: containerd CLI
- [ ] `kubectx`: switch Kubernetes contexts quickly
- [ ] `kubens`: switch Kubernetes namespaces quickly
- [ ] `ansible-doc`: inspect Ansible module/plugin docs locally
- [ ] `ansible-config`: inspect effective Ansible configuration

## Dev / Data

- [ ] `sqlite3`: inspect and query SQLite databases
- [ ] `npx`: run Node package binaries without permanent install
- [ ] `yarn`: alternative Node package manager
- [ ] `uv`: fast Python package/project tool
- [ ] `ruff`: fast Python linter/formatter
- [ ] `pytest`: Python test runner
- [ ] `cargo`: Rust package/build tool
- [ ] `rustc`: Rust compiler
- [ ] `java`: JVM launcher
- [ ] `zig`: Zig compiler/toolchain

## Git Workflows To Learn As Concepts

- [ ] `git reflog`: recover from bad moves and find previous branch/head states
- [ ] `git bisect`: binary-search for the commit that introduced a bug
- [ ] `git worktree`: keep multiple checkouts of one repo
- [ ] `git stash`: temporary work-in-progress storage
- [ ] `git rebase`: rewrite/replay commits deliberately
- [ ] `git cherry-pick`: copy specific commits between branches
- [ ] `git blame`: inspect line-level authorship/history
- [ ] `git restore`: restore paths from index/commits without old `checkout` ambiguity
- [ ] `git switch`: switch branches without old `checkout` ambiguity

## Second-Pass Lower-Priority Additions

These are still non-junk, but mostly become important when a specific debugging, build, media, storage, or admin task makes them relevant.

### Debug / Build Internals

- [ ] `gdb`: native debugger for C/C++ and low-level process inspection
- [ ] `readelf`: inspect ELF binaries and shared libraries
- [ ] `objdump`: disassemble and inspect object files/binaries
- [ ] `nm`: list symbols from object files and binaries
- [ ] `addr2line`: map program addresses back to source locations
- [ ] `strip`: remove symbols/debug info from binaries
- [ ] `ar`: create and inspect static library archives

### Media / Docs / Structured Text

- [ ] `ffmpeg`: media conversion, remuxing, extraction, and repair
- [ ] `ffprobe`: inspect media metadata and streams
- [ ] `gs`: Ghostscript CLI for PostScript/PDF processing
- [ ] `pdftocairo`: convert PDF pages to images/vector formats
- [ ] `pdftoppm`: convert PDF pages to bitmap images
- [ ] `xmllint`: validate, format, and query XML
- [ ] `xsltproc`: apply XSLT transforms to XML

### Storage / Network Edge Cases

- [ ] `blockdev`: inspect/set block device parameters
- [ ] `resizepart`: resize a partition entry without recreating it
- [ ] `iscsiadm`: manage iSCSI discovery, login, and sessions
- [ ] `networkctl`: inspect systemd-networkd link state
- [ ] `nsupdate`: dynamic DNS update client
- [ ] `tcptraceroute`: traceroute over TCP instead of ICMP/UDP

### VM / Security Extras

- [ ] `qemu-nbd`: expose QEMU disk images as network block devices
- [ ] `qemu-ga`: QEMU guest agent
- [ ] `virt-what`: detect whether the system is running inside a VM
- [ ] `virt-host-validate`: validate host setup for libvirt/KVM
- [ ] `pkexec`: run GUI/CLI programs via polkit authorisation
- [ ] `pkcs11-tool`: inspect and use PKCS#11 tokens/smartcards

### Misc System / Userland

- [ ] `update-alternatives`: manage default implementations for commands
- [ ] `rtcwake`: suspend/hibernate until a scheduled wake time
- [ ] `wall`: broadcast a message to logged-in users
- [ ] `write`: send a message to another logged-in user's terminal
- [ ] `sulogin`: single-user/rescue login shell

## Third-Pass Human-Usable Leftovers

Mostly niche, but still commands a person might deliberately run. This section is the boundary before package internals, daemons, generated helpers, GUI launchers, and language/toolchain debris.

### Core / GNU / Text Leftovers

- [ ] `arch`: print machine architecture, similar to `uname -m`
- [ ] `dircolors`: configure `ls` colour output
- [ ] `factor`: factor integers; mostly a curiosity, occasionally useful for quick maths
- [ ] `hostid`: print numeric host identifier
- [ ] `pinky`: lightweight `finger`-style user info
- [ ] `users`: list currently logged-in users
- [ ] `runcon`: run a command with a chosen SELinux context
- [ ] `shred`: overwrite a file before deleting it; useful to recognise, limited on SSDs/COW filesystems
- [ ] `diff3`: three-way file comparison
- [ ] `pcre2grep`: grep using PCRE2 regular expressions
- [ ] `pcre2test`: test/debug PCRE2 regular expressions
- [ ] `sum`: old checksum tool; recognise, prefer stronger hashes
- [ ] `b2sum`: BLAKE2 checksums
- [ ] `base32`: base32 encode/decode
- [ ] `basenc`: encode/decode base16/base32/base64 variants
- [ ] `col`: filter reverse line feeds from old formatter output
- [ ] `colrm`: remove columns from text
- [ ] `recode-sr-latin`: Serbian Latin recoding helper
- [ ] `uconv`: Unicode conversion/transliteration tool
- [ ] `ul`: render underlining for terminals
- [ ] `unicode_start`: switch console to Unicode mode
- [ ] `unicode_stop`: leave console Unicode mode
- [ ] `unix2mac`: convert Unix line endings to old Mac line endings
- [ ] `mac2unix`: convert old Mac line endings to Unix line endings
- [ ] `cpio`: archive format/tool still seen in initramfs and legacy Unix contexts
- [ ] `diffstat`: summarise patch/diff size by file
- [ ] `combinediff`: combine incremental patches
- [ ] `dehtmldiff`: make HTML diffs easier to read as plain diffs

### Accounts / Auth / Admin

- [ ] `adduser`: friendlier user creation wrapper on some systems
- [ ] `chpasswd`: update passwords in batch
- [ ] `chgpasswd`: update group passwords in batch
- [ ] `chroot`: run a shell/command with a different root directory
- [ ] `cvtsudoers`: convert sudoers files between formats
- [ ] `authselect`: select/manage Fedora/RHEL authentication profiles
- [ ] `groupmems`: manage supplementary group membership
- [ ] `pwck`: check passwd/shadow file integrity
- [ ] `grpck`: check group/gshadow file integrity
- [ ] `newuidmap`: set UID mappings for user namespaces
- [ ] `newgidmap`: set GID mappings for user namespaces
- [ ] `run0`: systemd's sudo-like privilege escalation tool

### Accounting / Audit / SELinux Extras

- [ ] `ac`: show user connection-time accounting
- [ ] `accton`: enable/disable process accounting
- [ ] `lastcomm`: show previously executed commands from process accounting
- [ ] `sa`: summarise process accounting records
- [ ] `dump-acct`: print process accounting files in human-readable form
- [ ] `dump-utmp`: print utmp login/session records
- [ ] `aulast`: audit-log equivalent of `last`
- [ ] `aulastlog`: audit-log equivalent of `lastlog`
- [ ] `ausyscall`: map syscall names and numbers
- [ ] `avcstat`: show SELinux AVC statistics
- [ ] `chcat`: change SELinux security categories
- [ ] `checkmodule`: compile SELinux policy modules
- [ ] `checkpolicy`: compile SELinux policy
- [ ] `secon`: show SELinux context information
- [ ] `selinuxenabled`: test whether SELinux is enabled
- [ ] `setfiles`: set SELinux file contexts from policy

### Kernel / Console / Hardware Extras

- [ ] `choom`: inspect/adjust OOM killer score
- [ ] `cpupower`: inspect/tune CPU power management
- [ ] `chcpu`: configure CPUs online/offline
- [ ] `chmem`: configure memory online/offline
- [ ] `ctrlaltdel`: configure Ctrl-Alt-Del behaviour
- [ ] `wdctl`: inspect watchdog devices
- [ ] `kbd_mode`: inspect/set keyboard mode
- [ ] `chvt`: switch virtual terminals
- [ ] `deallocvt`: deallocate unused virtual terminals
- [ ] `dumpkeys`: dump keyboard translation tables
- [ ] `showkey`: show keycodes/scancodes
- [ ] `setfont`: load console font
- [ ] `setterm`: set terminal attributes
- [ ] `showconsolefont`: show current console font glyphs
- [ ] `lsgpu`: list GPU devices
- [ ] `lsipc`: list System V IPC facilities
- [ ] `lsirq`: list IRQ information
- [ ] `lslocks`: list file locks
- [ ] `lslogins`: inspect user/login metadata
- [ ] `usb-devices`: detailed USB device listing
- [ ] `udisksctl`: manage disks through UDisks from the CLI
- [ ] `upower`: inspect battery/power devices

### Storage / Filesystem Leftovers

- [ ] `addpart`: tell the kernel about a partition
- [ ] `delpart`: tell the kernel to forget a partition
- [ ] `dmsetup`: low-level device-mapper management
- [ ] `dmstats`: device-mapper statistics
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
- [ ] `kpartx`: create device maps from partition tables
- [ ] `fuse-overlayfs`: userspace overlay filesystem, common for rootless containers
- [ ] `fuse2fs`: mount ext filesystems through FUSE
- [ ] `fusermount`: unmount FUSE filesystems
- [ ] `fusermount3`: unmount FUSE3 filesystems
- [ ] `mount.fuse`: mount FUSE filesystems
- [ ] `mount.fuse3`: mount FUSE3 filesystems
- [ ] `mkfs.exfat`: create exFAT filesystems
- [ ] `mkfs.f2fs`: create F2FS filesystems
- [ ] `mkfs.vfat`: create FAT/VFAT filesystems
- [ ] `dump.exfat`: inspect exFAT on-disk metadata
- [ ] `tune.exfat`: tune exFAT filesystem metadata
- [ ] `ntfs-3g`: mount NTFS read/write in userspace
- [ ] `ntfsclone`: clone NTFS filesystems efficiently
- [ ] `ntfsfix`: fix common NTFS problems / schedule Windows check
- [ ] `ntfsinfo`: inspect NTFS metadata
- [ ] `ntfslabel`: read/set NTFS label
- [ ] `ntfsls`: list NTFS filesystem contents
- [ ] `ntfsresize`: resize NTFS filesystems
- [ ] `ntfsundelete`: recover deleted files from NTFS
- [ ] `swaplabel`: read/set swap area label/UUID

### Btrfs / Thin-Provisioning Edge Cases

- [ ] `btrfsck`: legacy alias/wrapper for Btrfs check/repair
- [ ] `btrfs-convert`: convert ext filesystems to Btrfs in place
- [ ] `btrfs-find-root`: find Btrfs roots after damage
- [ ] `btrfs-image`: create/restore Btrfs metadata images
- [ ] `btrfs-map-logical`: map Btrfs logical extents to physical locations
- [ ] `btrfs-select-super`: recover by selecting a Btrfs backup superblock
- [ ] `btrfstune`: tune Btrfs filesystem parameters
- [ ] `compsize`: calculate compression ratio for Btrfs files
- [ ] `cache_check`: validate device-mapper cache metadata
- [ ] `cache_dump`: dump device-mapper cache metadata
- [ ] `cache_repair`: repair device-mapper cache metadata
- [ ] `thin_check`: validate thin-provisioning metadata
- [ ] `thin_dump`: dump thin-provisioning metadata
- [ ] `thin_ls`: list thin-provisioned volumes/snapshots
- [ ] `thin_repair`: repair thin-provisioning metadata
- [ ] `thin_restore`: restore thin-provisioning metadata

### Networking / Services Leftovers

- [ ] `ab`: ApacheBench HTTP benchmarking
- [ ] `GET`: simple command-line HTTP GET client from libwww-perl
- [ ] `HEAD`: simple command-line HTTP HEAD client from libwww-perl
- [ ] `POST`: simple command-line HTTP POST client from libwww-perl
- [ ] `apachectl`: control Apache/httpd
- [ ] `arp`: inspect/manipulate ARP cache; mostly legacy beside `ip neigh`
- [ ] `arpaname`: convert IP addresses to reverse-DNS ARPA names
- [ ] `arptables-save`: dump ARP filtering rules
- [ ] `arptables-restore`: restore ARP filtering rules
- [ ] `arptables-translate`: translate ARP rules to nftables form
- [ ] `clockdiff`: measure clock difference between hosts
- [ ] `delv`: DNS lookup with DNSSEC validation
- [ ] `dhcpcd`: DHCP client
- [ ] `dnsdomainname`: show DNS domain name
- [ ] `dnstap-read`: read dnstap DNS logs
- [ ] `ipmaddr`: inspect multicast addresses; mostly legacy
- [ ] `iptables-nft-save`: save nft-backed iptables rules
- [ ] `iptables-nft-restore`: restore nft-backed iptables rules
- [ ] `iptables-translate`: translate iptables rules to nftables syntax
- [ ] `ip6tables-save`: save IPv6 iptables rules
- [ ] `ip6tables-restore`: restore IPv6 iptables rules
- [ ] `mii-tool`: inspect old Ethernet link state; mostly superseded by `ethtool`
- [ ] `mmcli`: ModemManager CLI
- [ ] `netstat`: legacy network/socket tool; prefer `ss` and `ip`
- [ ] `nstat`: network statistics counters
- [ ] `oping`: send ICMP echo requests with richer output
- [ ] `resolvconf`: manage resolver configuration on systems that use it
- [ ] `route`: legacy routing table tool; prefer `ip route`
- [ ] `rpcclient`: Samba/MS-RPC client for Windows/Samba diagnostics
- [ ] `smbget`: wget-like SMB downloader
- [ ] `smbstatus`: inspect Samba sessions/locks
- [ ] `smbtree`: browse SMB workgroups/shares
- [ ] `teamdctl`: inspect/control network team devices
- [ ] `wpa_passphrase`: generate WPA/WPA2 PSK config blocks
- [ ] `openvpn`: OpenVPN client/server
- [ ] `vpnc`: Cisco-compatible VPN client

### Bluetooth / Thunderbolt / Mobile

- [ ] `adb`: Android Debug Bridge
- [ ] `bluetoothctl`: Bluetooth control shell
- [ ] `btmgmt`: lower-level Bluetooth management shell
- [ ] `btmon`: Bluetooth packet/event monitor
- [ ] `btattach`: attach serial Bluetooth controllers
- [ ] `boltctl`: manage Thunderbolt devices
- [ ] `fwupdmgr`: firmware updates via fwupd
- [ ] `fwupdtool`: lower-level fwupd tool

### Systemd / Boot / Shutdown Leftovers

- [ ] `halt`: halt the machine; usually prefer `systemctl poweroff`
- [ ] `service`: legacy service wrapper; useful on mixed distros
- [ ] `kernel-install`: install/remove kernel images using systemd conventions
- [ ] `oomctl`: inspect systemd-oomd state
- [ ] `systemd-firstboot`: initialise basic settings on a new image
- [ ] `systemd-inhibit`: run a command while blocking sleep/shutdown
- [ ] `systemd-notify`: send readiness/status notifications from services
- [ ] `systemd-path`: inspect systemd/user path locations
- [ ] `systemd-socket-activate`: test socket-activated services
- [ ] `systemd-tty-ask-password-agent`: handle systemd password prompts
- [ ] `systemd-umount`: unmount through systemd
- [ ] `userdbctl`: inspect systemd user/group records
- [ ] `varlinkctl`: inspect/call Varlink services

### Containers / Virtualisation Leftovers

- [ ] `bwrap`: Bubblewrap sandbox/container setup utility
- [ ] `criu`: checkpoint/restore in userspace
- [ ] `qemu-io`: test/debug QEMU disk images
- [ ] `qemu-system-i386`: run 32-bit x86 system emulation
- [ ] `virt-admin`: administer libvirt daemons
- [ ] `virt-qemu-run`: run VM images directly through libvirt/QEMU tooling
- [ ] `virt-ssh-helper`: helper for SSH access via libvirt
- [ ] `virt-viewer`: view VM graphical consoles
- [ ] `virt-xml`: edit libvirt XML safely-ish from CLI
- [ ] `virt-xml-validate`: validate libvirt XML

### Build / Dev Leftovers

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
- [ ] `gcov`: GCC coverage reporting
- [ ] `c++filt`: demangle C++ symbols
- [ ] `ctags`: generate source navigation tags
- [ ] `gettext`: translate strings / inspect gettext tooling
- [ ] `gettextize`: add gettext infrastructure to a source tree
- [ ] `msgfmt`: compile gettext `.po` files
- [ ] `msgmerge`: merge gettext translations with updated templates
- [ ] `gmake`: GNU make command name on systems where `make` may differ
- [ ] `pkgconf`: `pkg-config` compatible implementation
- [ ] `objcopy`: copy/transform object files and binary sections
- [ ] `yasm`: assembler
- [ ] `dwz`: optimise DWARF debug info
- [ ] `debuginfod-find`: fetch debug info/source files from debuginfod servers
- [ ] `dtrace`: user-space static probe generation / tracing frontend
- [ ] `bats`: Bash Automated Testing System
- [ ] `check-regexp`: test regular expressions from the command line
- [ ] `doxygen`: generate API documentation from source

### Language Runtime Helpers

- [ ] `perl`: Perl interpreter
- [ ] `perldoc`: read Perl documentation
- [ ] `cpan`: install/query Perl modules from CPAN
- [ ] `corelist`: query which Perl modules shipped with which Perl versions
- [ ] `pip3`: Python package installer alias
- [ ] `pydoc3`: Python documentation browser
- [ ] `python3-config`: Python build flags for compiling extensions
- [ ] `idle3`: Python's basic GUI IDE
- [ ] `luajit`: LuaJIT interpreter

### Data / Formats / Documents

- [ ] `chardetect`: detect text encoding
- [ ] `csv2ods`: convert CSV to OpenDocument spreadsheet
- [ ] `json_pp`: pretty-print JSON
- [ ] `json_verify`: validate JSON
- [ ] `markdown_py`: render Markdown via Python-Markdown
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

### Images / Audio / Video Leftovers

- [ ] `ffplay`: quick media playback/debugging from FFmpeg
- [ ] `ghostscript`: PostScript/PDF interpreter; usually invoked as `gs`
- [ ] `convert`: legacy ImageMagick conversion command; prefer `magick` on newer systems
- [ ] `compare`: ImageMagick visual/image comparison
- [ ] `display`: ImageMagick image viewer
- [ ] `animate`: ImageMagick image sequence viewer
- [ ] `composite`: ImageMagick image compositing
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

- [ ] `lp`: submit files to print
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

### Security / Crypto / Smartcard Leftovers

- [ ] `gpg-agent`: GnuPG private-key agent
- [ ] `gpgconf`: inspect/configure GnuPG components
- [ ] `gpg-connect-agent`: talk directly to `gpg-agent`
- [ ] `gpgv`: verify OpenPGP signatures only
- [ ] `keyctl`: manage Linux kernel keyrings
- [ ] `pinentry`: password/PIN prompt used by GnuPG
- [ ] `rhash`: compute many hash formats
- [ ] `unshadow`: combine passwd/shadow for password audit tools
- [ ] `openpgp-tool`: inspect/use OpenPGP smartcards
- [ ] `opensc-tool`: inspect smartcards through OpenSC
- [ ] `p11tool`: GnuTLS PKCS#11 tool
- [ ] `pkcs15-tool`: inspect/use PKCS#15 smartcards
- [ ] `cardos-tool`: inspect CardOS smartcards
- [ ] `danetool`: GnuTLS DANE helper
- [ ] `dbxtool`: manage UEFI dbx revocation data
- [ ] `clevis`: policy-based decryption framework
- [ ] `clevis-luks-bind`: bind LUKS unlocking to TPM2/Tang/SSS policy
- [ ] `clevis-luks-list`: list Clevis bindings on a LUKS device
- [ ] `clevis-luks-unbind`: remove Clevis bindings
- [ ] `clevis-luks-unlock`: unlock a Clevis-bound LUKS device
- [ ] `cracklib-check`: check password strength against cracklib

### Package / Distro Maintenance Leftovers

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

### Personal / Interactive Apps Exposed As Commands

- [ ] `brave-browser`: launch Brave from the shell
- [ ] `calibre`: ebook manager
- [ ] `ebook-viewer`: Calibre ebook viewer
- [ ] `mpv`: media player
- [ ] `nano`: simple terminal editor
- [ ] `qwen`: Qwen CLI/local model tool if you use it
- [ ] `speedtest`: network speed test CLI
- [ ] `speedtest-cli`: Python speed test CLI
- [ ] `thunderbird`: launch Thunderbird from the shell
- [ ] `xsel`: X11 clipboard tool
- [ ] `zeal`: offline API/doc browser
- [ ] `zoom`: launch Zoom from the shell

## Cleanup Notes For Main File

- [ ] Fix the stray tmux paragraph appended to the `true` entry.
- [ ] Fix the extra leading space before the `rm` bullet.
- [ ] Add backticks around `declare`.
- [ ] Consider changing “Everything from your system's PATH” to “High-value commands from my PATH, triaged.”
