# Linux Basic Commands

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

Linux provides hundreds of commands, but you only need to know the **basics** to start working effectively. This guide lists the most common Linux commands with short descriptions.

---

## 📂 File and Directory Management

| Command | Description |
|---------|-------------|
| `pwd` | Print current working directory |
| `ls` | List files and directories |
| `ls -lah` | List with details (permissions, size, hidden files) |
| `cd <dir>` | Change directory |
| `mkdir <dir>` | Create a new directory |
| `mkdir -p a/b/c` | Create nested directories |
| `rmdir <dir>` | Remove an empty directory |
| `rm -rf <dir>` | Remove a directory with contents (⚠ dangerous) |
| `touch file.txt` | Create an empty file |
| `cp file1 file2` | Copy a file |
| `cp -r dir1 dir2` | Copy a directory recursively |
| `mv file1 file2` | Move or rename a file |
| `stat file.txt` | Show detailed file information |

---

## 📑 File Viewing and Editing

| Command | Description |
|---------|-------------|
| `cat file.txt` | Show file content |
| `less file.txt` | View file with scrolling (press `q` to quit) |
| `head -n 10 file.txt` | Show first 10 lines |
| `tail -n 10 file.txt` | Show last 10 lines |
| `tail -f file.log` | Follow file changes (useful for logs) |
| `nano file.txt` | Open file in nano editor |
| `vim file.txt` | Open file in vim editor |

---

## 🔍 Searching and Finding

| Command | Description |
|---------|-------------|
| `find /path -name "*.txt"` | Find files by name |
| `grep "pattern" file.txt` | Search for a word in a file |
| `grep -i "pattern" file.txt` | Case-insensitive search |
| `grep -R "pattern" /dir` | Recursive search in directory |
| `wc -l file.txt` | Count lines in a file |
| `sort file.txt` | Sort lines alphabetically |
| `uniq file.txt` | Remove duplicate lines |

---

## 👤 User and Permission Management

| Command | Description |
|---------|-------------|
| `whoami` | Show current logged-in user |
| `id` | Show user ID and groups |
| `adduser user1` | Create a new user (Debian/Ubuntu) |
| `useradd user1` | Create a new user (RHEL/CentOS) |
| `passwd user1` | Set password for user |
| `groups user1` | Show groups of a user |
| `chmod 755 file.sh` | Change file permissions |
| `chown user:group file.txt` | Change file owner and group |
| `sudo command` | Run command as superuser |

---

## ⚙️ Process and System Monitoring

| Command | Description |
|---------|-------------|
| `ps aux` | Show running processes |
| `top` | Live process monitoring |
| `htop` | Advanced process monitoring (install separately) |
| `kill <PID>` | Kill process by ID |
| `kill -9 <PID>` | Force kill a process |
| `uptime` | Show how long system has been running |
| `free -h` | Show memory usage |
| `df -h` | Show disk usage |
| `du -sh <dir>` | Show size of a directory |
| `uname -a` | Show system information |
| `hostnamectl` | Show system hostname and OS details |

---

## 🌐 Networking Commands

| Command | Description |
|---------|-------------|
| `ip a` | Show network interfaces and IPs |
| `ip r` | Show routing table |
| `ping google.com` | Test connectivity |
| `curl -I https://example.com` | Fetch HTTP headers |
| `wget https://file.com/file.zip` | Download a file |
| `scp file.txt user@host:/path` | Copy file over SSH |
| `rsync -avz file user@host:/path` | Sync files over SSH |
| `ss -tulpn` | Show listening ports and services |
| `traceroute google.com` | Trace network path (install if missing) |

---

## 📦 Package Management

### Debian/Ubuntu (`apt`)
| Command | Description |
|---------|-------------|
| `sudo apt update` | Update package list |
| `sudo apt upgrade -y` | Upgrade all packages |
| `sudo apt install nginx -y` | Install a package |
| `sudo apt remove nginx -y` | Remove a package |

### RHEL/CentOS (`dnf`/`yum`)
| Command | Description |
|---------|-------------|
| `sudo dnf update -y` | Update system |
| `sudo dnf install nginx -y` | Install a package |
| `sudo dnf remove nginx -y` | Remove a package |

---

## 📦 Archiving and Compression

| Command | Description |
|---------|-------------|
| `tar -cvf files.tar dir/` | Create a tar archive |
| `tar -xvf files.tar` | Extract a tar archive |
| `tar -czvf files.tar.gz dir/` | Create compressed tar.gz |
| `tar -xzvf files.tar.gz` | Extract compressed tar.gz |
| `zip -r files.zip dir/` | Create a zip archive |
| `unzip files.zip` | Extract a zip archive |
| `gzip file.txt` | Compress file |
| `gunzip file.txt.gz` | Decompress file |

---

## ⏰ Scheduling and Automation

| Command | Description |
|---------|-------------|
| `crontab -e` | Edit cron jobs |
| `crontab -l` | List cron jobs |
| `at 10:00` | Schedule a one-time job |
| `systemctl status cron` | Check cron service (Debian/Ubuntu) |
| `systemctl status crond` | Check cron service (RHEL/CentOS) |

---

## 📝 Summary

- Learn to **navigate the filesystem** with `ls`, `cd`, `pwd`.  
- Manage **files and directories** with `cp`, `mv`, `rm`, `mkdir`.  
- Search with `grep`, `find`, `wc`.  
- Monitor system with `ps`, `top`, `df`, `free`.  
- Manage networking with `ip`, `ping`, `scp`, `ss`.  
- Install software with `apt`, `dnf`, or other package managers.  

---

## 📚 Next Steps

- Practice these commands daily inside your Linux VM.  
- Combine commands with pipes (`|`) and redirection (`>`).  
- Move on to **permissions, users, and services**.  
- Explore shell scripting for automation.  

