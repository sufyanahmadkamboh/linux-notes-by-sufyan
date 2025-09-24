# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔎 Linux `find` Command – Complete Guide

The `find` command in Linux is one of the most **powerful tools** for searching files and directories based on name, type, size, permissions, modification time, and much more. It allows you to perform **automated actions** (delete, move, execute) on the files it finds.

---

## 📌 Basic Syntax

find [path] [options] [expression]

path → Directory where the search starts (use / for entire system, . for current directory).

options → Flags to control search (e.g., -type, -name).

expression → Conditions to match files or directories.

## 🚀 Common Examples

# 1️⃣ Find by Name
find /home -name "file.txt"


Search for file.txt inside /home.

Case-insensitive search:

find /home -iname "file.txt"

# 2️⃣ Find by File Type

Regular files:

find . -type f


Directories:

find . -type d


Symbolic links:

find . -type l

# 3️⃣ Find by Size

Files larger than 100 MB:

find / -type f -size +100M


Files smaller than 10 KB:

find / -type f -size -10k


Files exactly 1 GB:

find / -type f -size 1G

# 4️⃣ Find by Time

Modified in the last 7 days:

find /var/log -type f -mtime -7


Modified more than 30 days ago:

find /var/log -type f -mtime +30


Accessed within 24 hours:

find /home -atime -1

# 5️⃣ Find by Permission

Files with 777 permissions:

find . -type f -perm 777


Files owned by root:

find / -user root

# 6️⃣ Execute Actions on Found Files

Delete all .tmp files:

find /tmp -type f -name "*.tmp" -exec rm -f {} \;


Move .log files to /backup:

find /var/log -type f -name "*.log" -exec mv {} /backup \;


Change permissions of all .sh files:

find . -type f -name "*.sh" -exec chmod +x {} \;

# 7️⃣ Combine Multiple Conditions

Find .log files larger than 10 MB:

find /var/log -type f -name "*.log" -size +10M


Find files owned by user1 and modified in last 2 days:

find /home -user user1 -mtime -2

## 📂 Special Usage Examples
Exclude a Directory
find / -path "/proc" -prune -o -type f -name "*.conf" -print


(Search everywhere except /proc).

Find and Count Files
find . -type f | wc -l


(Counts total number of files).

Find with xargs for Efficiency
find . -type f -name "*.log" | xargs grep "ERROR"


(Search all .log files for the word “ERROR”).

## ⚡ Practical Use Cases

Locate large files eating disk space

Clean up old log files automatically

Search configuration files across /etc

Audit files with incorrect permissions

Automate bulk file operations