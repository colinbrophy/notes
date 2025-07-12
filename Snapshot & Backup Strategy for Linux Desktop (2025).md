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
    

### 2. **Local Project Data**

- **Examples**: Code checkouts, local dev environments, notes, build trees
    
- **Traits**: Often recoverable but inconvenient to lose
    
- **Approach**: Snapshot regularly and back up selectively with pruning
    
- **Snapshot?** Yes
    
- **Backup?** Yes (optional if low value)
    

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
    

> 💡 Ansible (or similar tools) is ideal here — it captures what you've changed and why, helping rebuild and audit your system over time. Snapshots can save you from accidents, but config management lets you know what _matters_.

### 5. "App data"

- **Examples**: Docker volumes, Podman images, Flatpak data, Libvirt VMs, Browser profiles
    
- **Traits**: Mixed user data and software, complex state
    
- **Approach**: Separate snapshot/backup logic, tool-aware
    
- **Snapshot?** If quiescent
    
- **Backup?** Yes
    

### 6. **Ephemeral** `/var` **Data**

- **Examples**: `/var/log`, `/var/cache`, `/var/tmp`, `/var/spool`
    
- **Traits**: Regenerable, transient
    
- **Approach**: Exclude from snapshots and backups
    
- **Snapshot?** No
    
- **Backup?** No
    

### 7. **Essential** `/var` **State**

- **Examples**: `/var/lib/rpm`, `/var/lib/systemd`, `/var/lib/NetworkManager`
    
- **Traits**: Needed for consistent rollback
    
- **Approach**: Snapshot with system
    
- **Snapshot?** Yes
    
- **Backup?** Optional
    

### 8. **Secrets and Credentials**

- **Examples**: SSH keys, GPG keys, Password vaults
    
- **Approach**: Password manager, with backups
    
- **Snapshot?** Yes for convenient restore 
    
- **Backup?** Yes (securely)
    
---

## 📌 Summary Table

| Category              | Snapshot   | Backup | Notes                         |
| --------------------- | ---------- | ------ | ----------------------------- |
| User Data             | ❌          | ✅      | Dedup + archive               |
| Local Project Data    | ✅          | ✅      | Snapshots + prune old backups |
| Installed Software    | ✅          | ❌      | Use snapshots                 |
| Config Files          | ✅/Optional | ✅      | Git + backup                  |
| Containers / Flatpaks | ⚠️         | ✅      | Use tool-aware backups        |
| Ephemeral /var        | ❌          | ❌      | Always exclude                |
| Essential /var State  | ✅          | ✅/❌    | Snapshot for system integrity |
| Secrets/Credentials   | ✅          | ✅      | Use encrypted vault or repo   |

---

## 🧠 Final Thought

Snapshots are not backups. They are useful for quick system rollback, but **user data and virtualised environments require separate, deliberate handling**.

System config is the hardest to track — use Git or Ansible to record what you've done. **Local projects are easy to move but annoying to lose**, so snapshots and pruneable backups are well worth it.

Match the tool to the data, not the other way around.