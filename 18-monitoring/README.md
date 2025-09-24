# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 📊 Linux Monitoring Commands – `df`, `du`, `free`, `top`

Monitoring in Linux is essential for **system performance, resource usage, and troubleshooting**.  
These basic commands help you check **disk space, memory usage, and running processes**.

---

## 🗂️ Disk Monitoring with `df`

### Show Disk Space Usage

df

Human-Readable Output
df -h


Output example:

Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   20G   28G  42% /

Show File System Types
df -Th


## ✅ Use Case: Check if disks are filling up.

## 📁 Disk Usage per Directory with du

Show Size of a Directory
du /var/log

Human-Readable Sizes
du -h /var/log

Summarize Total Size
du -sh /var/log

Show Sizes of All Subdirectories
du -sh /home/*


## ✅ Use Case: Find which folders are consuming the most space.

## 🧠 Memory Monitoring with free

Show Memory Usage
free

Human-Readable
free -h


Output example:

              total        used        free      shared  buff/cache   available
Mem:           16G         8G        4.5G        512M        3.5G        7.2G
Swap:          2G         512M       1.5G


total → Total RAM

used → Used RAM

free → Unused RAM

buff/cache → Memory used for caching

available → Memory available for new applications

## ✅ Use Case: Check if your server is running low on memory.

## ⚡ Process & Resource Monitoring with top

Run top
top


Displays real-time system stats:

CPU usage

Memory usage

Running processes

Useful Keys in top

q → Quit

k → Kill a process (enter PID)

M → Sort by memory usage

P → Sort by CPU usage

h → Help

## 📈 Alternative: htop (Interactive Viewer)

Install:

sudo apt install htop -y   # Debian/Ubuntu
sudo yum install htop -y   # CentOS/RHEL


Run:

htop


Provides colorful, interactive monitoring (easy navigation with arrows).

## ✅ Try it Yourself

Use df -h to check your root (/) partition usage.

Find the largest directory in /var using du -sh.

Use free -h to check available memory.

Run top, sort processes by memory (M) and CPU (P).

Install and try htop for a better visualization.