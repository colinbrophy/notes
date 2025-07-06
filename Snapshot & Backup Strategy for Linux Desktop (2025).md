## Overview

This note outlines a strategy for handling different types of data on a Linux desktop using a combination of Btrfs snapshots, backup tools (e.g. Borg), and version control (e.g. Git). Each category of data requires its own approach, based on mutability, recoverability, and user importance.

---

## 🔹 Categories of Data

### 1. **User Data**

- **Examples**: Documents, Photos, Videos, Emails, Bookmarks, Notes
    
- **Traits**: Irreplaceable, mutable
    
- **Approach**: Back up with deduplication tools like Borg or Restic
    
- **Snapshot?** No
    
- **Backup?** Yes
    

### 2. **Replaceable Local Data**

- **Examples**: Code checkouts, downloaded installers, build artefacts
    
- **Traits**: Re-creatable
    
- **Approach**: Exclude from backup unless modified
    
- **Snapshot?** Optional
    
- **Backup?** Only if irreplaceable or customised
    

### 3. **System Software**

- **Examples**: `/usr`, `/bin`, `/lib`, Flatpak system-level installs
    
- **Traits**: Immutable, managed by package manager
    
- **Approach**: Snapshots only
    
- **Snapshot?** Yes
    
- **Backup?** No
    

### 4. **System & User Config**

- **Examples**: `/etc`, `~/.config`, dotfiles, systemd units
    
- **Traits**: Small, important, usually text
    
- **Approach**: Version control with Git + backup
    
- **Snapshot?** Optional
    
- **Backup?** Yes
    

### 5. **Containerised/Virtualised Environments**

- **Examples**: Docker volumes, Podman images, Flatpak data, Libvirt VMs
    
- **Traits**: Mixed user data and software, complex state
    
- **Approach**: Separate snapshot/backup logic, tool-aware
    
- **Snapshot?** If quiescent
    
- **Backup?** Yes
    

### 6. **Ephemeral `/var` Data**

- **Examples**: `/var/log`, `/var/cache`, `/var/tmp`, `/var/spool`
    
- **Traits**: Regenerable, transient
    
- **Approach**: Exclude from snapshots and backups
    
- **Snapshot?** No
    
- **Backup?** No
    

### 7. **Essential `/var` State**

- **Examples**: `/var/lib/rpm`, `/var/lib/systemd`, `/var/lib/NetworkManager`
    
- **Traits**: Needed for consistent rollback
    
- **Approach**: Snapshot with system
    
- **Snapshot?** Yes
    
- **Backup?** Optional
    

### 8. **Secrets and Credentials**

- **Examples**: SSH keys, GPG keys, Password vaults
    
- **Approach**: Back up securely, often encrypted, versioned separately
    
- **Snapshot?** No
    
- **Backup?** Yes (securely)
    

---

## ⛏️ Recommended Subvolume Layout (Btrfs)

```
@root       => /
@home       => /home
@etc        => /etc
@var_log    => /var/log (exclude from snapshots)
@var_lib_vm => /var/lib/libvirt (optional)
@var_lib_ctr=> /var/lib/containers (optional)
```

---

## 📌 Summary Table

|Category|Snapshot|Backup|Notes|
|---|---|---|---|
|User Data|❌|✅|Dedup + archive|
|Local Clones/Builds|❌|❌/✅|Only if custom|
|Installed Software|✅|❌|Use snapshots|
|Config Files|✅/Optional|✅|Git + backup|
|Containers / Flatpaks|⚠️|✅|Use tool-aware backups|
|Ephemeral /var|❌|❌|Always exclude|
|Essential /var State|✅|✅/❌|Snapshot for system integrity|
|Secrets/Credentials|❌|✅|Use encrypted vault or repo|

---

## 🧠 Final Thought

Snapshots are not backups. They are useful for quick system rollback, but **user data and virtualised environments require separate, deliberate handling**. Match the tool to the data, not the other way around.