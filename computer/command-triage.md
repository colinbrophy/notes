#ai-written 
# Command Triage: What to Learn vs Ignore

Everything from your system's PATH, categorised.

- First of all learn meta commands like man and apropos.
## TIER 1: Core daily drivers (you almost certainly know these)

```
# Shell basics
bash                # your shell
zsh                 # alternative shell (fish also listed)
fish                # friendly interactive shell
cd                  # change directory
pwd                 # print working directory
ls                  # list files
dir                 # basically ls
vdir                # verbose ls
cp                  # copy
mv                  # move/rename
rm                  # remove
rmdir               # remove empty dirs
mkdir               # make dirs
ln                  # links (hard + symlinks)
touch               # create/update timestamps
cat                 # concatenate/display files
less                # pager
more                # worse pager
head                # first N lines
tail                # last N lines (tail -f for log following)
echo                # print text
printf              # formatted print
read                # read input in scripts
test                # conditional evaluation ([ ])
true                # exit 0
false               # exit 1
yes                 # repeat string forever

# Text processing
grep                # pattern search
egrep               # extended regex grep (deprecated, use grep -E)
fgrep               # fixed-string grep (deprecated, use grep -F)
sed                 # stream editor
awk                 # pattern/action language
gawk                # GNU awk
sort                # sort lines
uniq                # deduplicate adjacent lines
wc                  # word/line/byte count
cut                 # extract fields
tr                  # translate/delete characters
tee                 # split stdout to file + pipe
xargs               # build commands from stdin
diff                # compare files
patch               # apply diffs
comm                # compare sorted files line by line
paste               # merge lines side by side
column              # format into columns
fold                # wrap lines
fmt                 # simple text formatter
expand              # tabs to spaces
unexpand            # spaces to tabs
rev                 # reverse lines
tac                 # reverse file (cat backwards)
nl                  # number lines

# File operations
find                # search filesystem
chmod               # change permissions
chown               # change ownership
chgrp               # change group
stat                # file metadata
file                # detect file type
realpath            # resolve symlinks
readlink            # read symlink target
basename            # strip directory from path
dirname             # strip filename from path
mktemp              # create temp file/dir
install             # copy with permissions
link                # create hard link
unlink              # remove single file

# Archiving/compression
tar                 # tape archive (tar czf, tar xzf)
gzip                # .gz compression
gunzip              # .gz decompression
zcat                # view .gz without decompressing
bzip2               # .bz2 compression
bunzip2             # .bz2 decompression
bzcat               # view .bz2
xz                  # .xz compression
unxz                # .xz decompression
xzcat               # view .xz
zstd                # zstandard compression (fast)
zip                 # .zip creation
unzip               # .zip extraction
cpio                # archive format (used by rpm, initramfs)

# Process management
ps                  # process list
kill                # send signal
killall             # kill by name
pgrep               # find process by pattern
pkill               # kill by pattern
top                 # process monitor
htop                # better process monitor
bg                  # background job
fg                  # foreground job
jobs                # list shell jobs
nohup               # survive logout
wait                # wait for background jobs
nice                # set priority
renice              # change priority
timeout             # run with time limit

# System info
uname               # system info
hostname            # hostname
hostnamectl         # systemd hostname management
uptime              # load/uptime
date                # date/time
cal                 # calendar
who                 # logged in users
whoami              # current user
id                  # user/group IDs
groups              # group membership
env                 # environment variables
printenv            # print env vars

# Disk/filesystem
df                  # disk free space
du                  # disk usage
mount               # mount filesystems
umount              # unmount
lsblk               # block device list
fdisk               # partition table editor
parted              # another partition editor
sfdisk              # scriptable fdisk
mkfs.ext4           # create ext4
mkfs.xfs            # create xfs
mkfs.btrfs          # create btrfs
mkfs.fat            # create FAT
fsck                # filesystem check (+ fsck.ext4, fsck.xfs, etc.)
tune2fs             # ext filesystem params
blkid               # filesystem UUIDs/types
findmnt             # show mount tree
mkswap              # create swap
swapon              # enable swap
swapoff             # disable swap
sync                # flush writes

# Networking core
ip                  # modern network config (replaces ifconfig)
ss                  # socket statistics (replaces netstat)
ping                # ICMP echo
traceroute          # trace packet path
tracepath           # similar, no root needed
dig                 # DNS lookup
nslookup            # older DNS lookup
host                # simple DNS lookup
curl                # HTTP client
wget                # download files

# User management
useradd             # create user
userdel             # delete user
usermod             # modify user
groupadd            # create group
groupdel            # delete group
groupmod            # modify group
passwd              # change password
chpasswd            # batch password changes
chage               # password expiry
su                  # switch user
sudo                # execute as root
visudo              # edit sudoers safely
newgrp              # change active group

# Systemd
systemctl           # service/unit management
journalctl          # log viewer
loginctl            # session management
timedatectl         # time/timezone
localectl           # locale settings
hostnamectl         # hostname (listed above too)
coredumpctl         # manage core dumps

# Package management
dnf                 # Fedora/RHEL package manager
dnf5                # next-gen dnf
rpm                 # low-level rpm operations
yum                 # legacy alias for dnf

# Git
git                 # version control
gitk                # GUI log viewer
git-receive-pack    # server-side git
git-upload-pack     # server-side git
git-upload-archive  # server-side git
git-shell           # restricted shell for git-only SSH

# SSH
ssh                 # remote shell
scp                 # remote copy
sftp                # remote file transfer
ssh-keygen          # key generation
ssh-copy-id         # deploy public key
ssh-agent           # key agent
ssh-add             # add key to agent
ssh-keyscan         # grab host keys
sshd                # SSH daemon
sshpass             # non-interactive SSH password (use keys instead)

# Editors
nvim                # your editor
vim                 # fallback
vi                  # minimal vim
view                # read-only vim
nano                # simple editor
ed                  # line editor (for scripts)
```

---

## TIER 2: High-value tools to invest in learning

```
# Modern CLI replacements — big quality-of-life wins
fd                  # fast, intuitive find replacement. Pairs with fzf
rg                  # ripgrep — fast recursive grep with sane defaults
bat                 # cat with syntax highlighting and git integration
fzf                 # fuzzy finder — transforms how you navigate
fzf-tmux            # fzf inside tmux panes
zoxide              # smarter cd with frecency tracking
delta               # beautiful git diffs, pairs with lazygit
btop                # gorgeous process/resource monitor
ncdu                # interactive disk usage explorer — find what's eating space
lazygit             # TUI git client you already use
tree                # directory tree view

# Shell scripting quality
shellcheck          # static analysis for shell scripts — catches real bugs
shfmt               # shell script formatter (use with conform.nvim)
envsubst            # substitute env vars in templates — handy for deploy scripts
parallel            # GNU parallel — run jobs in parallel properly

# Data wrangling
jq                  # JSON query/transform — essential for API work, terraform state
yq                  # YAML equivalent of jq — critical for ansible debugging
column              # (listed above) tabular formatting

# Infrastructure debugging
lsof                # what has this file/port/socket open
strace              # (via stap/dtrace) — syscall tracing, find why things hang
tcpdump             # packet capture — the ground truth for network issues
nmap                # network scanner/port auditor
ncat                # netcat from nmap — TCP/UDP swiss army knife
arping              # ARP-level ping — find IP conflicts on L2
ethtool             # NIC stats, driver info, link detection
iotop               # per-process I/O usage
nethogs             # per-process bandwidth usage
mtr                 # traceroute + ping combined, ongoing
dmesg               # kernel ring buffer — hardware events, driver issues
dmidecode           # hardware inventory from BIOS tables
lshw                # detailed hardware listing
lspci               # PCI devices (GPUs, NICs, storage controllers)
lsusb               # USB devices
smartctl            # disk SMART health data — critical for your RAID setups
hdparm              # disk parameters and benchmarks

# Disk/storage (relevant to your Proxmox + RAID + ZFS work)
mdadm               # software RAID management
cryptsetup          # LUKS disk encryption
wipefs              # clear filesystem signatures before repurposing disks
blkdiscard          # TRIM/discard entire block device
fstrim              # periodic TRIM for SSDs
resize2fs           # resize ext filesystems
xfs_growfs          # grow XFS filesystem
xfs_repair          # repair XFS
xfs_info            # XFS filesystem info
btrfs               # btrfs management (if you use it on Fedora)
e2fsck              # ext filesystem check
dumpe2fs            # ext filesystem info
dd                  # block copy (careful with this one)
losetup             # loop device management

# Firewall/security (directly relevant to your iptables_autoblock work)
iptables            # legacy packet filtering (your current autoblock script)
iptables-save       # dump rules
iptables-restore    # load rules
ip6tables           # same for IPv6
nft                 # nftables — the modern replacement
firewall-cmd        # firewalld CLI
iptables-nft        # iptables syntax over nftables backend
ebtables            # ethernet bridge filtering
ipset               # IP sets for efficient rule matching
arptables           # ARP table filtering

# SELinux (Rocky Linux means you deal with this)
getenforce          # check SELinux mode
setenforce          # set SELinux mode
sestatus            # SELinux status
semanage            # manage SELinux policy
restorecon          # fix file contexts
chcon               # change file context
setsebool           # set SELinux booleans
getsebool           # get SELinux booleans
audit2allow         # generate policy from denials
audit2why           # explain SELinux denials
semodule            # manage SELinux modules
matchpathcon        # check expected context for path

# Containers (Fedora native)
podman              # rootless containers — docker-compatible
skopeo              # inspect/copy container images without pulling
buildah             # (not listed but related) build OCI images
crun                # container runtime (low-level)
conmon              # container monitor (low-level)

# Virtualisation (Proxmox/libvirt work)
virsh               # libvirt CLI — VM management
virt-install        # create VMs
virt-clone          # clone VMs
virt-manager        # GUI VM manager
qemu-img            # disk image creation/conversion
qemu-kvm            # KVM hypervisor
qemu-system-x86_64  # full system emulator

# Certificate/TLS (relevant to your Caddy + internal PKI work)
openssl             # cert inspection, CSR generation, TLS debugging
certtool            # GnuTLS cert tool
trust               # manage system trust store
update-ca-trust     # refresh CA bundle
p11-kit             # PKCS#11 module management

# Backup/recovery (your ReaR + restic stack)
rear                # Relax-and-Recover — bare metal DR
restic              # deduplicated encrypted backups
rsync               # file sync (also listed in tier 1)

# Samba/CIFS (law firm Windows interop)
smbclient           # SMB file access
mount.cifs          # mount SMB shares
cifscreds           # manage CIFS credentials
smbcacls            # SMB ACLs

# NFS (if used between Proxmox nodes)
mount.nfs           # NFS mount
mount.nfs4          # NFSv4 mount
nfsstat             # NFS statistics
showmount           # list NFS exports
exportfs            # manage NFS exports
rpcinfo             # RPC service info

# LVM (likely on your OVH servers)
pvcreate            # create physical volume
vgcreate            # create volume group
lvcreate            # create logical volume
pvs                 # list PVs
vgs                 # list VGs
lvs                 # list LVs
pvdisplay           # PV detail
vgdisplay           # VG detail
lvdisplay           # LV detail
lvextend            # grow LV
lvresize            # resize LV
lvremove            # delete LV
vgextend            # add PV to VG

# Process/resource tuning
sysctl              # kernel parameter tuning
ionice              # I/O priority
taskset             # CPU affinity
ulimit              # resource limits
prlimit             # per-process limits
coresched           # core scheduling
chrt                # real-time scheduling

# Audit/logging (server hardening)
auditctl            # audit rule management
auditd              # audit daemon
aureport            # audit reports
ausearch            # search audit logs
augenrules          # generate audit rules from files

# Misc high-value
tmux                # terminal multiplexer
screen              # (not listed but tmux is better)
watch               # repeat command and watch output
ipcalc              # subnet calculator
openconnect         # VPN client (if you use it)
openvpn             # OpenVPN client
chronyc             # NTP client management
timedatectl         # (listed above) time sync status
```

---

## TIER 3: Good to know exist, learn when needed

```
# Text/doc conversion
pandoc              # universal doc converter — markdown to PDF, docx, etc.
img2pdf             # images to PDF
ocrmypdf            # OCR + PDF optimization — useful for law firm doc scanning
tesseract           # OCR engine behind ocrmypdf
dos2unix            # fix Windows line endings
unix2dos            # create Windows line endings
iconv               # character encoding conversion
uchardet            # detect character encoding

# System admin situational
chattr              # set file attributes (immutable flag for hardening)
lsattr              # list file attributes
getfacl             # read POSIX ACLs
setfacl             # set POSIX ACLs
fuser               # find process using file/mount
lslocks             # list file locks
lsns                # list namespaces
nsenter             # enter namespace
unshare             # create namespace
chroot              # change root (basic containment)
pivot_root          # swap root filesystem
modprobe            # load kernel module
modinfo             # kernel module info
lsmod               # list loaded modules
insmod              # insert module (prefer modprobe)
rmmod               # remove module
depmod              # generate module deps
kexec               # fast reboot into new kernel
dracut              # generate initramfs
grubby              # manage boot entries
bootctl             # systemd-boot management
grub2-mkconfig      # regenerate grub config

# Network situational
bridge              # bridge management
tc                  # traffic control (QoS)
dcb                 # data centre bridging
devlink             # devlink device management
rdma                # RDMA management
vdpa                # vDPA management
tipc                # TIPC protocol
iw                  # wireless config
wpa_cli             # WPA supplicant control
wpa_supplicant      # WPA auth daemon
nmcli               # NetworkManager CLI
nm-online           # wait for network
rfkill              # enable/disable radios
dnsmasq             # lightweight DNS/DHCP server
avahi-daemon        # mDNS/DNS-SD daemon
avahi-browse        # browse mDNS services
avahi-resolve       # resolve mDNS names

# Debugging / tracing
gdb                 # GNU debugger
stap                # SystemTap — kernel/userspace tracing
ltrace              # (not listed but related to strace)
perf                # (via intel tools) performance counters
eu-addr2line        # address to source line (elfutils)
eu-readelf          # ELF inspection
eu-nm               # symbol listing
eu-objdump          # object file disassembly
eu-strings          # extract strings from binaries
eu-stack            # stack traces
objdump             # object file analysis
readelf             # ELF file analysis
nm                  # symbol table
strings             # extract printable strings
ldd                 # shared library dependencies
ldconfig            # library cache management
sprof               # shared library profiling

# Disk / filesystem edge cases
badblocks           # scan for bad blocks
debugfs             # ext filesystem debugger
filefrag            # file fragmentation
e2image             # ext filesystem image
e4defrag            # ext4 defragment
compsize            # btrfs compression stats
btrfs-convert       # convert ext to btrfs
mkisofs             # create ISO images
genisoimage         # create ISO (same thing)
isohybrid           # make ISO bootable from USB
xorriso             # advanced ISO manipulation
mount.ntfs-3g       # mount NTFS
ntfsfix             # quick NTFS repair
ntfsresize          # resize NTFS
ntfslabel           # set NTFS label
exfatlabel          # exFAT label
mount.fuse3         # FUSE mount
fuse-overlayfs      # overlay filesystem in user namespace

# Cron / scheduling
crontab             # (tier 1 really) cron job management
anacron             # run missed cron jobs
at                  # one-shot scheduled command
atq                 # list at queue
atrm                # remove at job
batch               # run when load is low

# Systemd extended
systemd-analyze     # boot performance analysis
systemd-cgls        # cgroup tree
systemd-cgtop       # cgroup resource usage
systemd-run         # transient units
systemd-nspawn      # lightweight container
systemd-resolve     # DNS resolution debugging (resolvectl)
systemd-cat         # pipe to journal
systemd-escape      # escape strings for unit names
systemd-tmpfiles    # manage temp files
systemd-sysusers    # manage system users declaratively
systemd-mount       # mount via systemd
systemd-dissect     # inspect disk images
systemd-creds       # credential management
systemd-cryptenroll # LUKS2 token enrollment
systemd-repart      # declarative partitioning
systemd-detect-virt # detect virtualisation type
machinectl          # manage containers/VMs (systemd-nspawn)
portablectl         # portable services
homectl             # systemd-homed user management
importctl           # import VM/container images
resolvectl          # DNS resolver management

# Development tools (if building from source)
make                # build tool
gcc                 # C compiler
g++                 # C++ compiler
cpp                 # C preprocessor
as                  # assembler
ld                  # linker
ar                  # archive tool (static libs)
ranlib              # index archives
objcopy             # copy/transform object files
strip               # strip symbols
autoconf            # generate configure scripts
automake            # generate Makefiles
m4                  # macro processor
flex                # lexer generator
bison               # parser generator
cmake               # (not listed but related)
cargo               # Rust package manager
rustc               # Rust compiler
rustdoc             # Rust documentation
go                  # Go compiler
gofmt               # Go formatter
node                # Node.js runtime
npm                 # Node package manager
npx                 # Node package runner
yarn                # alternative Node package manager
pip                 # Python package installer
pip3                # Python 3 pip
python3             # Python 3
pydoc3              # Python docs

# Quota management (multi-tenant servers)
quota               # show quotas
quotacheck          # scan filesystem for quotas
quotaon             # enable quotas
quotaoff            # disable quotas
edquota             # edit user quotas
repquota            # quota report
setquota            # set quota non-interactively

# SCSI/iSCSI (if applicable to OVH storage)
iscsiadm            # iSCSI initiator management
iscsid              # iSCSI daemon

# Clevis/LUKS auto-unlock (if you do NBDE)
clevis              # policy-based decryption framework
clevis-luks-bind    # bind LUKS to clevis policy
clevis-luks-unlock  # auto-unlock LUKS
clevis-encrypt-tang # tang server encryption
clevis-decrypt      # decrypt clevis token

# IPMI/hardware management
ipmaddr             # (limited) multicast management

# Misc useful
cloc                # count lines of code
croc                # simple encrypted file transfer between machines
just                # command runner (you already use this)
stow                # symlink farm manager (your dotfiles)
direnv              # per-directory env vars
mods                # AI in the terminal (if you use it)
ollama              # local LLM inference (your GPU passthrough setup)
gh                  # GitHub CLI
yt-dlp              # video downloader
rclone              # cloud storage sync (S3, etc.)
terraform           # infrastructure as code (your stack)
terraform-ls        # terraform language server
vagrant             # VM provisioning (your ansible testing)
syncthing           # p2p file sync
jd                  # JSON diff
w3m                 # terminal web browser
glow                # terminal markdown renderer
cheat               # cheat sheets in terminal
```

---

## TIER 4: Niche / special-purpose (ignore until relevant)

```
# Graphviz (useful if you ever generate architecture diagrams as code)
dot                 # directed graph layout
neato               # undirected graph layout
circo               # circular layout
fdp                 # force-directed layout
sfdp                # scalable force-directed
twopi               # radial layout
gvpr                # graph pattern/action language
acyclic             # make digraph acyclic
gvpack              # merge graph layouts

# ImageMagick (image processing)
magick              # ImageMagick v7
convert             # image conversion (legacy)
identify            # image info
mogrify             # in-place image edit
composite           # overlay images
animate             # animate images
compare             # diff images
montage             # create image montage
display             # show image
import              # screenshot
conjure             # run ImageMagick scripts
stream              # stream image data

# FFmpeg (media processing)
ffmpeg              # video/audio conversion
ffplay              # media player
ffprobe             # media info

# Printing (law firms might actually print)
lp                  # print
lpr                 # BSD print
lpq                 # print queue
lprm                # remove print job
lpstat              # printer status
lpadmin             # printer admin
cancel              # cancel print job
cupsd               # CUPS daemon
cupsctl             # CUPS config
cupsfilter          # CUPS filter chain
cups-browsed        # browse network printers

# Scanner
scanimage           # scanner CLI
simple-scan         # GUI scanner

# HPLIP (HP printers — law firms love HP)
hp-setup            # HP printer setup
hp-info             # HP printer info
hp-scan             # HP scanner
hp-clean            # HP print head cleaning
hp-levels           # ink levels
hp-testpage         # test page

# Samba extended (deeper Windows interop)
rpcclient           # raw RPC calls to Windows
smbcquotas          # SMB quota management
smbcacls            # (listed above) ACL management
smbget              # wget-like SMB download
smbtree             # browse SMB network
nmblookup           # NetBIOS lookup

# GlusterFS (if you use it)
gluster             # GlusterFS CLI
glusterfs           # GlusterFS client
glusterfsd          # GlusterFS daemon
mount.glusterfs     # mount GlusterFS

# HashiCorp Vault (not listed but relevant to your stack)
# (vault binary not in this list)

# Ansible tools (not listed but core to your work)
# (ansible, ansible-playbook, etc. not in this list)

# LibreOffice CLI (doc conversion without GUI)
libreoffice         # LibreOffice suite
soffice             # LibreOffice headless
oocalc              # calc alias
oowriter            # writer alias
unoconv             # document converter via LibreOffice

# Subversion (legacy, but some orgs still use it)
svn                 # SVN client
svnadmin            # SVN repository admin
svnlook             # SVN repo inspection

# Mercurial
hg                  # Mercurial VCS

# X11/Wayland tools
xauth               # X11 auth
xhost               # X11 access control
xset                # X11 settings
xprop               # X11 window properties
xmodmap             # X11 keyboard mapping
xrdb                # X11 resource database
setxkbmap           # keyboard layout
Xwayland            # X11 compatibility layer
wl-copy             # Wayland clipboard copy
wl-paste            # Wayland clipboard paste
xsel                # X11 clipboard

# Bluetooth
bluetoothctl        # Bluetooth management
btmon               # Bluetooth monitor
btmgmt              # Bluetooth management
btattach            # attach serial Bluetooth

# GStreamer (media framework)
gst-launch-1.0      # construct/run media pipeline
gst-inspect-1.0     # inspect GStreamer elements

# D-Bus tools
dbus-send           # send D-Bus messages
dbus-monitor        # watch D-Bus
busctl              # systemd D-Bus tool
gdbus               # GLib D-Bus tool
dbus-daemon         # D-Bus daemon

# Flatpak
flatpak             # Flatpak package manager

# Power management
powertop            # power usage analysis
powerstat           # power stats
turbostat           # CPU frequency/power
x86_energy_perf_policy  # CPU energy policy
cpupower            # CPU frequency management

# Sensors
sensors             # hardware temperature/voltage/fan readings
sensors-detect      # detect sensor chips

# NILFS2 (log-structured filesystem — very niche)
nilfs-clean         # NILFS2 garbage collection
nilfs-tune          # NILFS2 params
mkfs.nilfs2         # create NILFS2

# NBD (network block device)
nbdkit              # NBD server toolkit
nbdcopy             # copy NBD data
nbdinfo             # NBD server info

# AppStream / desktop metadata
appstreamcli        # AppStream metadata tool
desktop-file-validate  # validate .desktop files
desktop-file-install    # install .desktop files

# Wacom / input
libwacom-list-local-devices  # list tablets
libinput             # input device management

# Video acceleration (Intel)
vainfo              # VA-API info
h264encode          # H.264 VA-API encode
hevcencode          # HEVC VA-API encode
vp8enc              # VP8 encode
vp9enc              # VP9 encode
av1encode           # AV1 encode

# Modem management
mmcli               # ModemManager CLI
ModemManager        # modem daemon
qmicli              # QMI modem interface
mbimcli             # MBIM modem interface

# SNMP / InfiniBand
ibstat              # IB status
ibhosts             # IB hosts
ibping              # IB ping
ibswitches          # IB switches
perfquery           # IB performance query
# (extensive ib* tools — ignore unless you have IB fabric)

# Passt (user-mode networking)
passt               # user-mode TCP/UDP proxy
pasta               # same, TAP variant

# Mtools (FAT filesystem from userspace — for bootable USBs)
mdir                # list FAT directory
mcopy               # copy to/from FAT
mdel                # delete on FAT
mformat             # format FAT
mlabel              # FAT volume label

# Squashfs
mksquashfs          # create squashfs image
unsquashfs          # extract squashfs
sqfscat             # cat from squashfs
```

---

## TIER 5: Safely ignore (system plumbing, desktop apps, TeX, etc.)

```
# GNOME desktop applications
gnome-calculator    gnome-calendar     gnome-characters
gnome-clocks        gnome-connections  gnome-contacts
gnome-control-center gnome-disks       gnome-extensions
gnome-extensions-app gnome-firmware    gnome-font-viewer
gnome-help          gnome-keyring      gnome-logs
gnome-maps          gnome-session      gnome-shell
gnome-software      gnome-system-monitor gnome-text-editor
gnome-tour          gnome-tweaks       gnome-weather
gnome-boxes         gnome-browser-connector
baobab              # disk usage GUI
nautilus            # file manager
loupe               # image viewer
papers              # PDF viewer
epiphany            # GNOME web browser
yelp                # help viewer
zenity              # GUI dialogs from scripts
seahorse            # keyring GUI
drawing             # drawing app
easyeffects         # audio effects GUI
orca                # screen reader
ptyxis              # GNOME terminal
mediawriter         # Fedora media writer

# Other desktop apps (you know what these are)
brave-browser       brave-browser-stable
google-chrome       google-chrome-stable
firefox
thunderbird
slack
zoom
steam
meld                # diff GUI
virt-viewer         # VM console viewer
solaar              # Logitech device manager
ghostty             # your terminal (just runs)
mpv                 # media player
scrcpy              # Android screen mirror

# TeX/LaTeX (entire typesetting ecosystem — 100+ commands)
latex               pdflatex           lualatex
xelatex             bibtex             biber
texhash             mktexlsr           kpsewhich
dvips               dvipdfmx           makeindex
luatex              luajit             fmtutil
updmap              texlua             texluac
mktexfmt            mktexpk            mktextfm
# ... and dozens more tex-related tools

# ABRT crash reporting
abrt-cli            abrtd              abrt-applet
abrt-auto-reporting abrt-dbus
# ... and all abrt-action-* abrt-dump-* abrt-harvest-*

# Braille / accessibility
brltty              brltty-atb         brltty-ctb
brltty-ktb          brltty-trtxt       brltty-ttb
xbrlapi             file2brl

# TPM tools (unless doing measured boot / NBDE)
tpm2                tpm2_create        tpm2_getcap
tpm2_pcrread        tpm2_seal          tpm2_unseal
# ... and 80+ tpm2_* / tss2_* commands

# Smart card tools
opensc-tool         opensc-explorer    pkcs11-tool
pkcs15-tool         pkcs15-crypt       pkcs15-init
cardos-tool         cryptoflex-tool    piv-tool
gids-tool           goid-tool          iasecc-tool
sc-hsm-tool         westcos-tool       openpgp-tool
dnie-tool           npa-tool           dtrust-tool
egk-tool            eidenv

# GPG internals (gpg itself is useful, but these are plumbing)
gpg-agent           gpgconf            gpg-connect-agent
gpgparsemail        gpgsplit           gpgtar
gpg-wks-client      gpg-wks-server     dirmngr
dirmngr-client      gpg-mail-tube      g13
g13-syshelp         kbxutil            watchgnupg
gpg-error           gpgme-json

# Perl internals
cpan                cpansign           enc2xs
encguess            h2ph               h2xs
instmodsh           libnetcfg          piconv
pl2pm               pod2html           pod2man
pod2text            pod2usage          podchecker
prove               ptar               ptardiff
ptargrep            corelist           splain
perldoc             perlbug            perlthanks
json_pp             shasum             streamzip
zipdetails          xsubpp

# Python internals
pydoc               pygmentize         pyinotify

# GLib/GObject/GI build tools
glib-compile-resources   glib-compile-schemas
glib-genmarshal          glib-gettextize
glib-mkenums             g-ir-compiler
g-ir-scanner             g-ir-generate
g-ir-inspect             gi-compile-repository
gi-decompile-typelib     gi-inspect-typelib
gobject-query

# GTK build tools
gtk-update-icon-cache    gtk-query-immodules-2.0-32
gtk-query-immodules-2.0-64   gtk-query-immodules-3.0-32
gtk-query-immodules-3.0-64   gtk4-builder-tool
gtk4-encode-symbolic-svg     gtk4-query-settings
gtk4-update-icon-cache       gtk4-path-tool

# Vala compiler
vala                valac               vapigen
vala-gen-introspect

# GDK/Pango
gdk-pixbuf-csource  gdk-pixbuf-pixdata
gdk-pixbuf-query-loaders-32  gdk-pixbuf-query-loaders-64
pango-list          pango-view          pango-segmentation

# Font tools
fc-cache            fc-list             fc-match
fc-query            fc-scan             fc-validate
fc-cat              fc-conflist         mkfontdir
mkfontscale         ttmkfdir

# Gettext/i18n
gettext             gettextize          gettext.sh
xgettext            msgfmt              msgmerge
msginit             msgcat              msgconv
msgen               msgexec             msgfilter
msggrep             msgunfmt            msguniq
msgattrib           msgcmp              msgcomm
ngettext            envsubst            # (envsubst is useful — listed in tier 2)
autopoint

# GDM (display manager internals)
gdm                 gdm-config          gdmflexiserver

# Ghostscript (PostScript interpreter)
gs                  ps2pdf              ps2ps
pdf2ps              eps2eps
# ... and many gs* variants

# rsvg / XML tools
rsvg-convert        xmllint             xmlcatalog
xsltproc            xmlsec1             xmlwf
xml2-config

# PipeWire internals (audio just works, don't touch)
pipewire            pipewire-pulse      pipewire-avb
pipewire-aes67      pw-cat              pw-cli
pw-config           pw-dot              pw-dump
pw-link             pw-loopback         pw-metadata
pw-mididump         pw-midiplay         pw-midirecord
pw-mon              pw-play             pw-profiler
pw-record           pw-reserve          pw-top
wpctl               wpexec              wireplumber
spa-inspect         spa-json-dump       spa-monitor
spa-resample        spa-acp-tool

# Speech
spd-say             spd-conf            speech-dispatcher
speak-ng            espeak-ng           flite
flite_cmu_us_kal    flite_cmu_us_slt    # ... and other flite voices

# Intel GPU debug (unless debugging i915/Xe specifically)
intel_gpu_top       intel_gpu_frequency intel_reg
intel_error_decode  intel_firmware_decode
intel_gtt           intel_backlight     intel_lid
# ... and 30+ intel_* tools

# i915/Xe perf
i915-perf-configs   i915-perf-control   i915-perf-reader
i915-perf-recorder  xe-perf-configs     xe-perf-control
xe-perf-reader      xe-perf-recorder

# VMware tools (if on VMware, otherwise ignore)
vmtoolsd            vmware-toolbox-cmd  vmware-rpctool
vmware-checkvm      vmhgfs-fuse         vm-support
# ... and other vmware-* tools

# VirtualBox guest (if on VBox, otherwise ignore)
VBoxClient          VBoxControl         VBoxService
VBoxDRMClient       VBoxClient-all      vboxwl

# HiP (AMD ROCm)
hipcc               hipconfig           rocm-smi

# ICU internals
icu-config          icuinfo

# Source-highlight
source-highlight    source-highlight-esc.sh
cpp2html            java2html

# libfido2 / FIDO
# (not explicitly listed but related to pam/security)

# CUPS PPD tools
ppdc                ppdhtml             ppdi
ppdmerge            ppdpo               cupstestppd

# Misc system plumbing never invoked directly
agetty              # terminal login
sulogin             # single-user login
switch_root         # initramfs pivot
pldd                # list loaded DSOs
ldattach            # line discipline
setterm             # terminal settings
showconsolefont     # console font
setfont             # set console font
showkey             # show keycodes
loadkeys            # load keymap
dumpkeys            # dump keymap
setleds             # keyboard LEDs
setkeycodes         # map scancodes to keycodes
unicode_start       # enable UTF-8 console
unicode_stop        # disable UTF-8 console
setmetamode         # console meta key
deallocvt           # deallocate VT
chvt                # change VT
openvt              # open new VT
resizecons          # resize console
fgconsole           # current VT number
kbdinfo             # keyboard info
kbd_mode            # keyboard mode
mapscrn             # load screen map
setvtrgb            # set VT RGB
consoletype         # (not listed) check console type
pam_namespace_helper    # PAM plumbing
pam_timestamp_check     # PAM plumbing
pwhistory_helper        # PAM plumbing
unix_chkpwd             # PAM plumbing
unix_update             # PAM plumbing
mkhomedir_helper        # PAM plumbing
```

---

## Summary: The "actually learn these" shortlist

If you're building Anki cards, focus here:

```
# Immediate ROI — build cards this week
jq                  # JSON wrangling (terraform state, API responses, structured logs)
yq                  # YAML wrangling (ansible vars, k8s manifests)
rg                  # fast grep across codebases and config trees
shellcheck          # catches real bugs in your bash scripts
ncdu                # "where did the disk space go" — interactive

# High ROI — build cards this month
fd                  # sane find, integrates with fzf
lsof                # "what's using this port/file"
tcpdump             # packet-level debugging
nmap                # network/port auditing
ss                  # socket stats (deeper than basic usage)
audit2allow         # SELinux troubleshooting on Rocky
semanage            # SELinux policy management
podman              # rootless containers
systemd-analyze     # boot/service performance
smartctl            # disk health monitoring
ipcalc              # quick subnet math

# Medium ROI — when the situation arises
parallel            # GNU parallel for batch operations
shfmt               # shell formatting (conform.nvim integration)
envsubst            # template variable substitution in deploy scripts
skopeo              # container image inspection
mtr                 # ongoing traceroute
dmesg               # hardware event debugging
wipefs              # disk reprovisioning
ipset               # efficient firewall rule matching
nbdkit              # network block device tools
clevis              # LUKS auto-unlock
```
