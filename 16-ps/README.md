# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🖥️ Process Monitoring with `ps` Command

The `ps` (process status) command is used to **view running processes** in Linux. It provides information like **PID, TTY, CPU usage, memory, and the command** that started the process. It’s a key tool for monitoring and troubleshooting.

---

## 📌 Basic Syntax

ps [options]

## 🚀 Common Usage Examples

# 1️⃣ Show Processes for Current Shell
ps


Output example:

  PID TTY          TIME CMD
 2321 pts/0    00:00:00 bash
 2350 pts/0    00:00:00 ps

# 2️⃣ Show All Processes
ps -e


or

ps -A

# 3️⃣ Show with Full Format
ps -f


Output includes UID, PID, PPID, start time, and command.

# 4️⃣ Show Processes for All Users
ps -ef


(Standard full-format listing used in many scripts).

# 5️⃣ Show by User
ps -u username

# 6️⃣ Display as a Tree
ps -ejH


or

ps axjf


Shows parent-child relationship between processes.

# 7️⃣ Show Specific PID
ps -p 1234

# 8️⃣ Combine with grep
ps -ef | grep nginx


Finds all running nginx processes.

## 📊 Important Columns

Column	Meaning
PID	Process ID (unique identifier)
PPID	Parent Process ID
UID	User who owns the process
TTY	Terminal associated with the process
CMD	Command that launched the process
TIME	CPU time used

## 🛠️ Useful Options

Option	Description
-e	All processes
-f	Full format (UID, PPID, etc.)
-u <user>	Show processes of a user
-p <pid>	Show process by PID
-o <format>	Customize output fields
-T	Show threads
--forest	Display hierarchy in a tree format

Example with custom format:

ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head


(Top processes by memory usage).

## ✅ Try it Yourself

Task 1: Run ps to see only your shell and ps command.

Task 2: Use ps -ef to view all system processes.

Task 3: Find your SSH session using ps -u <your-username>.

Task 4: Show top memory-using processes with custom formatting.