This table summarises core system-level capabilities across Linux (Fedora with GNOME), macOS, and Windows 11. It excludes superficial polish and focuses on architecture, control, stability, observability, and recovery.

| Feature                                   | **Linux (Fedora/GNOME)**                                  | **macOS**                                                 | **Windows 11**                                        |
| ----------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | ----------------------------------------------------- |
| **Window Management**                     | ✅ Dynamic workspaces, keyboard-driven, Wayland support    | ❌ No dynamic desktops, limited per-monitor support        | ⚠️ Basic snapping, no dynamic virtual desktops        |
| **Session Restore**                       | ❌ Not reliable yet (GNOME working on it)                  | ✅ App state saved/restored for native apps                | ⚠️ Limited, works for some Store apps only            |
| **Backup/Snapshot Tools**                 | ✅ Snapper, Timeshift, Btrfs snapshots, system rollbacks   | ⚠️ Time Machine (limited visibility, no boot integration) | ⚠️ File History only, no system snapshot restore      |
| **Display Server & DPI Handling**         | ✅ Wayland, per-monitor scaling, HDR s upport in progress  | ❌ Single pipeline, no fractional scaling                  | ⚠️ Basic multi-monitor scaling, inconsistent          |
| **Filesystem Features**                   | ✅ Btrfs/ZFS: snapshots, checksums, compression            | ⚠️ APFS snapshots, no checksums, opaque metadata          | ❌ NTFS: no snapshots, weak metadata handling          |
| **Auto-Updating / Transactional Updates** | ✅ ostree (Silverblue), dnf, rollbackable updates          | ⚠️ Smooth but non-rollbackable major updates              | ❌ Risky, frequent regressions, forced reboots         |
| **Logging & Diagnostics**                 | ✅ journalctl, abrt, structured, accessible                | ❌ Obscure, logs buried in Console.app                     | ⚠️ Event Viewer is clunky and fragmented              |
| **Terminal Tools & CLI UX**               | ✅ First-class, `bash`, `fish`, `systemctl`, etc.          | ⚠️ `zsh` okay but not core to workflow                    | ❌ `wt.exe` is still poor; PowerShell better but niche |
| **Package Management**                    | ✅ Native (dnf, rpm-ostree, Flatpak)                       | ❌ No system-level package manager                         | ❌ winget exists but bolt-on, Store is limited         |
| **Container Support**                     | ✅ podman, docker, nspawn, full namespaces                 | ❌ Only Docker (non-native)                                | ⚠️ WSL2 is a VM, not true containers                  |
| **Service Management**                    | ✅ systemd: units, sockets, timers, sandboxing             | ⚠️ launchd is powerful but opaque                         | ❌ Windows Services: ancient, poor tooling             |
| **Volume & Storage Management**           | ✅ LVM, Btrfs subvols, ZFS, growable partitions            | ⚠️ APFS containers, limited control                       | ❌ Basic partitioning only                             |
| **Crash Handling / Fallback Mode**        | ✅ Multi-TTY fallback, readable logs, recovery consoles    | ❌ GUI hangs often unclear, hidden state                   | ❌ BSOD visible, but no fallback environment           |
| **Filesystem Integrity Protection**       | ✅ Checksummed (Btrfs, ZFS), error detection               | ❌ APFS lacks full checksums                               | ❌ NTFS has no integrity features                      |
| **Live Patching**                         | ✅ kpatch/livepatch/ksplice (select distros)               | ❌ Requires reboot for kernel updates                      | ❌ Requires reboot                                     |
| **Power Management & Profiles**           | ✅ Tunable (TLP, power-profiles-daemon)                    | ❌ No control beyond GUI                                   | ⚠️ Registry hacks or OEM tools                        |
| **Hardware Interface Transparency**       | ✅ udev, `/proc`, `/sys`, full device visibility           | ❌ Mostly locked down                                      | ❌ Partially hidden via abstraction                    |
| **Swap Management**                       | ✅ Swap files, zswap, zram supported                       | ⚠️ Hidden from user                                       | ❌ Confusing mix of pagefile & hibernation             |
| **Bootloader & Recovery**                 | ✅ systemd-boot/GRUB, EFI-aware, boot snapshot integration | ❌ Opaque, boot stubs only                                 | ❌ Opaque, no snapshot boot, basic recovery mode       |

### 🖥️ Desktop-Focused Features

| Feature                     | Linux                           | macOS                             | Windows 11                                |
| --------------------------- | ------------------------------- | --------------------------------- | ----------------------------------------- |
| Multi-monitor setup         | ✅ Excellent, Wayland-aware      | ⚠️ Often glitchy with scaling     | ⚠️ Functional, but inconsistently applied |
| Keyboard workflow           | ✅ Strong: GNOME/KDE-driven      | ⚠️ Trackpad-focused, limited keys | ⚠️ Weak keyboard-centric support          |
| App theming & customisation | ✅ Fully customisable via themes | ❌ Mostly locked down              | ⚠️ Some theming, but inconsistent         |
| App integration             | ✅ Flatpak + portals improving   | ✅ Polished for native apps        | ❌ Store vs Win32 fragmentation            |
| Workspace isolation         | ✅ GNOME workspaces per monitor  | ❌ No real isolation               | ⚠️ Virtual desktops only                  |

### 💻 Laptop-Specific Features

| Feature                    | Linux                           | macOS             | Windows 11                  |
| -------------------------- | ------------------------------- | ----------------- | --------------------------- |
| Suspend/resume reliability | ⚠️ Varies by hardware           | ✅ Very reliable   | ✅ Generally reliable        |
| Battery life               | ⚠️ Needs tuning (TLP etc.)      | ✅ Very efficient  | ⚠️ Hardware/OEM dependent   |
| Display scaling (HiDPI)    | ✅ Fractional, Wayland-native    | ❌ Just 2x scaling | ⚠️ Inconsistent per-monitor |
| Touchpad gestures          | ✅ Good on libinput + GNOME      | ✅ Excellent       | ⚠️ Somewhat clunky          |
| Thermal management         | ✅ Configurable, sensors visible | ❌ Mostly closed   | ⚠️ OEM-specific tools       |
### 🔌 Compatibility & Integration Strengths

| Area                              | Linux                                     | macOS                            | Windows 11                                |
| --------------------------------- | ----------------------------------------- | -------------------------------- | ----------------------------------------- |
| Broad hardware support            | ⚠️ Good, but needs vendor alignment       | ✅ Excellent on Apple hardware    | ✅ Very broad, including legacy            |
| Third-party software availability | ✅ Good via package managers               | ✅ Wide availability (mac-native) | ✅ Extensive Win32 and UWP base            |
| Peripheral support                | ⚠️ Varies, especially proprietary devices | ✅ Excellent with certified gear  | ✅ Very good, especially OEM-specific      |
| Mobile device integration         | ⚠️ KDE Connect or GSConnect               | ✅ Tight iOS/macOS integration    | ⚠️ Android sync tools, no native SMS etc. |
| Commercial support ecosystem      | ⚠️ Canonical/Red Hat exist, but limited   | ✅ AppleCare, Apple stores        | ✅ OEMs, Microsoft Enterprise              |
### 🛡️ Security & Isolation Features

| Feature                        | Linux                              | macOS                          | Windows 11                           |
| ------------------------------ | ---------------------------------- | ------------------------------ | ------------------------------------ |
| Mandatory Access Control (MAC) | ✅ SELinux, AppArmor                | ❌ Not available                | ❌ Not available                      |
| Application sandboxing         | ✅ Flatpak, systemd, seccomp        | ✅ App sandboxing for App Store | ⚠️ UWP apps only, rest unrestricted  |
| Kernel hardening               | ✅ Grsecurity/SELinux stack         | ⚠️ Hardened, but closed        | ⚠️ Some protections, no user control |
| Software signing enforcement   | ⚠️ Optional, distro-dependent      | ✅ Strict signing model         | ✅ Strong for Store apps              |
| Encryption tooling             | ✅ LUKS, dm-crypt, TPM2 integration | ✅ FileVault + secure enclave   | ✅ BitLocker + TPM                    |
| Firmware update mechanism      | ✅ fwupd + LVFS                     | ✅ Apple firmware updates       | ⚠️ OEM-dependent                     |

**Legend**:

- ✅ Best-in-class or complete
    
- ⚠️ Usable but incomplete, limited, or opaque
    
- ❌ Lacks robust support or transparency
    

**Conclusion**: Linux (Fedora/GNOME) leads in nearly all low-level system features — especially in transparency, rollback, filesystem resilience, and service/tooling architecture. macOS remains strong for polished defaults but weak on observability and control. Windows retains hardware compatibility but trails in integrity, update safety, and modern architecture. For laptops and desktops alike, Linux gives maximum control and composability, albeit with some tuning required on laptops for battery and suspend behavior.

macOS and Windows, however, retain strong advantages in **default compatibility, polish, and vendor-integrated workflows**, especially for mainstream hardware and software use. These strengths are real — but arise more from controlled ecosystems than from system design itself.

### 📝 TODO: Potential Future Comparison Dimensions

- Software trust and distribution models (e.g. Flatpak vs App Store vs MSI)
    
- VPN and network isolation capabilities (per-app firewalls, namespace support)
    
- Update models (monolithic vs transactional vs delta)
    
- Crash reporting infrastructure and user control
    
- Telemetry defaults and privacy controls
    
- Multi-user and session isolation architecture
    
- System identity and authentication model (e.g. local vs cloud accounts)
    
- Filesystem layout and philosophy (FHS, sandboxing, `/usr` merge, etc.)