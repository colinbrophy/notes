- SSO Google workspace.
- Need to discuss boot times.
- Discuss how to deal with hardware failure:
	- How to make sure that we can recover fast, what are the options here in terms of:
		  - ROT
		  - RPO
	- Needs costs estimates for now much each of these are.



**Hardware failures**

- Disk/SSD failure (single or multiple in array)
- RAM failure causing corruption
- CPU/motherboard death
- PSU failure
- Network card or cabling
- GPU failure (relevant for your Quadro workloads)
- RAID controller failure (often worse than disk failure)

**Infrastructure failures**

- Power outage (short or extended)
- Cooling failure leading to thermal shutdown
- Network connectivity loss (upstream provider, DNS, routing)
- Datacentre-level outage (fire, flood, power grid)
- OVH-style incidents (remember the Strasbourg fire)

**Software/logical failures**

- OS corruption or failed update
- Filesystem corruption (ZFS can help but isn't immune)
- Database corruption
- Application bugs destroying data
- Failed migration or upgrade
- Container/VM configuration drift causing failures

**Human error** (often the biggest category)

- Accidental deletion (`rm -rf`, dropped database, deleted VM)
- Misconfiguration (firewall rules, DNS, permissions)
- Bad deployment or rollback failure
- Credential rotation gone wrong

**Security incidents**

- Ransomware encryption
- Data exfiltration requiring rebuild on clean infrastructure
- Compromised backups (if attacker had persistence)
- Supply chain compromise

**External/vendor**

- Provider bankruptcy or service termination
- API/service deprecation
- Certificate expiry (including upstream CAs)
- Domain expiry or registrar issues

Worth mapping each against your RTO/RPO to see where the gaps are.