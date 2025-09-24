# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔑 SSH (Secure Shell) Basics

**SSH (Secure Shell)** is a protocol that allows secure remote login and command execution over a network.  
It encrypts traffic, ensuring confidentiality and security when managing remote servers.

---

## 📌 Installing SSH

### On Ubuntu/Debian

sudo apt update
sudo apt install openssh-server -y

On CentOS/RHEL
sudo yum install openssh-server -y
sudo systemctl enable sshd
sudo systemctl start sshd


Check status:

sudo systemctl status ssh
# or
sudo systemctl status sshd

## 📌 Connecting to a Remote Server

ssh username@remote_ip


Example:

ssh ubuntu@192.168.1.10


If using a custom port (e.g., 2222):

ssh -p 2222 username@remote_ip

## 📌 First-Time Connection

When connecting for the first time, you’ll be asked to accept the host key:

Are you sure you want to continue connecting (yes/no)? yes

## 📌 SSH Keys (Passwordless Login)

Generate SSH Key Pair
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"


(Default location: ~/.ssh/id_rsa and id_rsa.pub)

Copy Public Key to Server
ssh-copy-id username@remote_ip


Now you can log in without a password:

ssh username@remote_ip

## 📌 Useful SSH Options

Run a command directly:

ssh user@server "uptime"


Enable verbose/debug output:

ssh -v user@server


Use specific identity file:

ssh -i ~/.ssh/mykey.pem user@server


Keep session alive:

ssh -o ServerAliveInterval=60 user@server

## 📂 SSH Configuration File (~/.ssh/config)

Example:

Host myserver
    HostName 192.168.1.10
    User ubuntu
    Port 22
    IdentityFile ~/.ssh/id_rsa


Then connect with:

ssh myserver

## 📌 Secure SSH Server (Best Practices)

Change default port (/etc/ssh/sshd_config → Port 2222)

Disable root login: PermitRootLogin no

Use SSH keys instead of passwords

Limit users with AllowUsers

Apply changes:

sudo systemctl restart sshd

## ✅ Try it Yourself

Install openssh-server on a VM.

Connect from another machine using ssh username@ip.

Generate an SSH key and configure passwordless login.

Run a remote command like uname -a via SSH.

Harden your SSH configuration (disable root login).