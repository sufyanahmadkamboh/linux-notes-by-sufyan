# Linux Introduction

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

Linux is a family of **open-source Unix-like operating systems** based on the Linux kernel. It is one of the most widely used platforms for servers, DevOps, networking, and cloud-native technologies. Most modern infrastructure (including Docker and Kubernetes) relies heavily on Linux.

---

## 📌 Why Learn Linux?

- **Servers & Cloud**: Linux is the backbone of AWS, Azure, GCP, and almost every container-based system.  
- **Automation Friendly**: Scriptable, reliable, and lightweight.  
- **Security & Stability**: Used for critical production environments.  
- **Community Support**: Huge open-source ecosystem.  

---

## 🚀 Role of Linux in DevOps

Linux plays a **central role in DevOps engineering**. Almost every DevOps tool and platform is either built for Linux or runs best on Linux-based environments. Key areas include:

1. **Server Management**  
   - Most production servers run on Linux.  
   - Knowledge of Linux commands is essential for provisioning, configuring, and troubleshooting.  

2. **Cloud & Virtualization**  
   - Cloud providers (AWS, Azure, GCP) rely heavily on Linux-based instances.  
   - Virtualization platforms (VMware, VirtualBox, KVM) and container runtimes (Docker, containerd) run on Linux.  

3. **Configuration Management & Automation**  
   - Tools like **Ansible, Puppet, Chef** require strong Linux knowledge.  
   - Shell scripting automates repetitive tasks.  

4. **Containers & Orchestration**  
   - **Docker** containers are based on Linux namespaces and cgroups.  
   - **Kubernetes** clusters run primarily on Linux nodes.  

5. **CI/CD Pipelines**  
   - Jenkins, GitLab CI, and GitHub Actions commonly run on Linux agents.  
   - Build and deployment pipelines often include Linux commands and scripts.  

6. **Monitoring & Logging**  
   - Tools like **Prometheus, Grafana, ELK, Splunk** are Linux-native.  
   - Logs (`/var/log/*`) and system monitoring require Linux skills.  

7. **Security & Networking**  
   - Firewalls, SELinux/AppArmor, SSH, VPNs, and certificates are managed on Linux.  
   - Networking commands (`ip`, `ss`, `iptables`, etc.) are essential for debugging.  

👉 **In short**: To be an effective DevOps engineer, Linux isn’t just optional—it’s the foundation.

---

## 🐧 Popular Linux Distributions

| Distribution | Package Manager | Use Case |
|--------------|----------------|----------|
| Ubuntu/Debian | `apt` | Beginner-friendly, widely used on servers |
| CentOS / Rocky / AlmaLinux | `dnf` / `yum` | Enterprise, RHEL-based |
| Arch Linux | `pacman` | Rolling release, bleeding-edge |
| openSUSE | `zypper` | Enterprise/desktop hybrid |
| Alpine Linux | `apk` | Lightweight, popular in containers |

---

## 📂 Linux Filesystem Hierarchy

Linux follows the **FHS (Filesystem Hierarchy Standard)**. Some key directories:

- `/` → Root directory  
- `/bin`, `/sbin` → Essential binaries (user/admin)  
- `/etc` → System configuration files  
- `/var` → Logs, cache, spool files  
- `/home` → User home directories  
- `/tmp` → Temporary files  
- `/opt` → Optional/add-on software  
- `/proc`, `/sys` → Kernel and system information  

---

## 🖥️ The Shell

The **shell** is a command-line interpreter (most common: `bash`, `zsh`).  
It allows you to run programs, chain commands, and automate tasks.  

Helpful tools:
- `man <command>` → Full manual  
- `<command> --help` → Quick usage help  
- `history` → See previously run commands  
- `CTRL + R` → Reverse search  

---

## 👤 Users, Groups, and Permissions

- Every user has a **UID**, and every group has a **GID**.  
- File permissions are split into **read (r), write (w), execute (x)** for:
  - Owner (user)
  - Group
  - Others  

Example:
-rw-r--r-- 1 user group file.txt
Here:
- `rw-` → user can read/write  
- `r--` → group can read only  
- `r--` → others can read only  

---

## 📑 Files & Directories

- Everything in Linux is a **file** (even devices and processes).  
- Files can be regular, directories, symbolic links, or special device files.  
- Common tasks:
  - Navigate (`pwd`, `cd`)
  - Create/remove (`mkdir`, `rm`)
  - Copy/move (`cp`, `mv`)
  - Links (`ln -s target linkname`)  

---

## 🔍 Text Processing & Searching

Linux provides powerful text manipulation tools:
- `cat`, `less`, `head`, `tail` → Viewing files  
- `grep` → Searching text patterns  
- `awk`, `sed` → Processing and transforming text  
- `sort`, `uniq`, `wc` → Sorting, counting, summarizing  

---

## ⚙️ Processes & Services

- **Processes**: Running programs (`ps`, `top`, `htop`, `kill`).  
- **Services**: Managed by **systemd** (`systemctl start|stop|status <service>`).  
- Jobs can run in foreground/background (`&`, `fg`, `jobs`).  

---

## 🌐 Networking Basics

Linux provides many networking utilities:
- `ip a` → Show network interfaces  
- `ping` → Test connectivity  
- `ss -tulpn` → Show open ports  
- `curl`, `wget` → Fetch data from URLs  
- `scp`, `rsync` → Copy files across servers  

---

## 📦 Package Management

Each distribution has its package manager:
- Ubuntu/Debian → `apt`  
- RHEL/CentOS/Rocky → `dnf` / `yum`  
- Arch → `pacman`  
- openSUSE → `zypper`  

These manage software installation, updates, and removal.

---

## 📊 Logs & Monitoring

- Logs → `/var/log` (e.g., `syslog`, `messages`, `dmesg`)  
- System monitoring:
  - `free -h` → Memory usage  
  - `df -h` → Disk usage  
  - `du -sh *` → Directory sizes  
  - `uptime` → System load  

---

## 🔐 Security Basics

- **Sudo**: Run commands with elevated privileges.  
- **SSH**: Secure remote login and file transfers.  
- **Firewall**: Use `ufw` (Ubuntu) or `firewalld` (RHEL).  
- Keep system patched with updates.  

---

## ✍️ Text Editors

- **Vim**: Powerful, modal editor.  
  - `:w` save, `:q` quit, `i` insert mode, `Esc` exit insert.  
- **Nano**: Simple editor.  
  - `Ctrl+O` save, `Ctrl+X` exit.  

---

## 🚀 Next Steps

- Explore Linux commands with a **cheat sheet** (provided separately in this repo).  
- Practice creating users, managing permissions, and writing shell scripts.  
- Learn to manage processes and monitor systems.  
- Move on to **networking, package management, and automation**.  

---

## 📚 Further Practice Ideas

- Set up a Linux VM in VirtualBox/VMware.  
- Practice SSH into your VM.  
- Write small shell scripts for automation.  
- Install and configure a simple web server (`nginx`/`apache`).  
- Monitor system logs and resources.  

