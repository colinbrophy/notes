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