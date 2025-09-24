# SSH Basics


bash
Copy code
ssh-keygen -t ed25519 -C "me@example.com"
ssh-copy-id user@server
ssh -i ~/.ssh/id_ed25519 user@server
Config: ~/.ssh/config

sshconfig
Copy code
Host prod
  HostName 203.0.113.10
  User ubuntu
  IdentityFile ~/.ssh/id_ed25519
