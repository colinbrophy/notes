#aidump
### Context or problem statement

Evaluating long-term, low-risk encrypted storage options that balance POSIX correctness, metadata leakage, durability, and future portability. Comparison spans userspace encryption, kernel-space encryption, network filesystems, and cloud-style storage backends.

### Key insights or conclusions

- **Userspace encryption**
    
    - gocryptfs is the best-maintained userspace encrypted filesystem today.
        
    - It is suitable for local disks and sync-style workflows.
        
    - It has unavoidable weaknesses: weakened fsync semantics and metadata leakage.
        
    - These weaknesses are structural, not bugs.
        
- **Kernel-space encryption**
    
    - eCryptfs was architecturally well suited for encrypted home directories and dev workflows.
        
    - It is now deprecated and effectively unmaintained.
        
    - fscrypt and LUKS are viable but have narrower scopes or coarser granularity.
        
- **Metadata leakage**
    
    - All stacked or overlay filesystems leak metadata such as file counts, sizes, and access patterns.
        
    - Userspace overlays cannot fully hide this.
        
    - Application-level encryption reduces expectations and avoids semantic lies.
        
- **Cryptomator model**
    
    - Cryptomator avoids POSIX promises entirely.
        
    - It offers better long-term durability and portability by treating storage as a dumb object store.
        
    - It is well suited for cloud or remote storage where correctness matters more than transparency.
        
- **Protocols**
    
    - WebDAV is a real IETF standard and is conservative, boring, and stable.
        
    - It does not pretend to offer POSIX semantics.
        
    - SMB and NFS assume LAN-like conditions and work well when those assumptions hold.
        
- **LAN and peered VPC**
    
    - SMB and NFS are safe over real LANs or peered VPCs due to low latency and stable links.
        
    - Over WAN or consumer cloud links, their semantics degrade badly.
        
    - TrueNAS provides POSIX-correct semantics on disk via ZFS; correctness still depends on client protocol and mount options.
        
- **Storage vs SaaS**
    
    - Treating providers as commodity storage is safer than relying on proprietary SaaS clients.
        
    - Open formats plus standard protocols age better than integrated sync solutions.
        

### Open questions or uncertainties

- Whether metadata leakage is acceptable depends on threat model.
    
- Whether POSIX transparency or long-term readability is the higher priority.
    
- How much operational complexity is acceptable for stronger guarantees.
    

### Next actions or follow-ups

- Decide between:
    
    - gocryptfs for local or sync-style encrypted directories
        
    - Cryptomator for long-term remote storage
        
- If using NFS with TrueNAS, define strict NFSv4 export and mount options.
    
- Document threat model explicitly before finalising architecture.