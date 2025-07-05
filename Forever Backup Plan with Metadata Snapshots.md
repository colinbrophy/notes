

**Goal:**  
Create a "never-ending time machine" backup system that:

- Stores all important user files permanently
- Avoids storing large, low-value files (e.g. media, downloads, VMs)
- Still tracks metadata of excluded files for auditing and reproducibility
- Can run indefinitely with efficient deduplication and pruning


**Strategy:**

1. **Use Borg for backup**
    
    - `borg` provides deduplication, compression, encryption, and reliable archives
        
    - Run backups frequently (e.g. daily or hourly)
        
    - Store archives in a secure, possibly offsite location
        
2. **Exclude large files and noisy directories**
    
    - An exclude file already exists and should be reviewed and expanded as needed
        
    - Example patterns to include:
        
        ```
        *.mp4
        *.iso
        *.mkv
        *.zip
        *.tar
        /home/colin/Downloads
        /home/colin/Videos
        /home/colin/VirtualMachines
        /home/colin/.cache
        ```
        
    - Use `--exclude-from=...` in `borg create` commands
        
3. **Capture metadata snapshots of excluded files**
    
    - Run a script to scan excluded areas:
        
        ```bash
        find /home/colin -type f \
          \( -iname '*.mp4' -o -size +200M \) \
          -exec stat --format='%n %s %y' {} \; \
          > ~/backup_metadata/$(date +%F)_bigfiles.txt
        ```
        
    - Optional: add hashes with `sha256sum`
        
    - Store metadata files in Git or archive them with `borg`
        
4. **Never prune the archive**
    
    - For long-term history, disable or minimise pruning:
        
        ```
        borg prune --keep-daily=all
        ```
        
    - Or use multiple repos: one pruned, one forever
        
5. **Optional: Custom metadata tracker**
    
    - Maintain a JSONL or SQLite log of excluded file metadata
        
    - Can be indexed, queried, and audited later
        

**Benefits:**

- Preserves all user-critical data
    
- Maintains traceability of excluded content
    
- Keeps backup size sustainable
    
- Enables future audits or backfills if needed