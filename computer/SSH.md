  ```bash
  # Generate key (no passphrase)
  ssh-keygen -t ed25519 -C "tggbackends-deploy" -f /tmp/tggbackends_deploy_key -N ""

  # View private key (for Ansible vault)
  cat /tmp/tggbackends_deploy_key

  # View public key (for GitHub deploy key)
  cat /tmp/tggbackends_deploy_key.pub

  # Cleanup
  rm /tmp/tggbackends_deploy_key /tmp/tggbackends_deploy_key.pub

  Add to Ansible Vault

  ansible-vault edit vault.yml

  tggbackends_deploy_key: |
    -----BEGIN OPENSSH PRIVATE KEY-----
    <paste key here>
    -----END OPENSSH PRIVATE KEY-----

  Add to GitHub

  Repo → Settings → Deploy keys → Add deploy key

  - Title: tggbackends-deploy
  - Key: paste public key
  - Allow write access: No (read-only is fine for cloning)
  
 ``` 

```bash
ssh-keygen -R 10.10.10.100
```

This removes the old host key entry. The next connection will prompt you to accept the new one (or Ansible will add it automatically if you have `host_key_checking = False` or `StrictHostKeyChecking=accept-new` configured).