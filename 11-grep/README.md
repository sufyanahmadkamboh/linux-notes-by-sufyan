# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔍 Linux `grep` Command – Complete Guide

The `grep` command is one of the most widely used tools in Linux. It allows you to **search text using patterns** (regular expressions) inside files or output from other commands. It’s an essential tool for log analysis, debugging, and system administration.

---

## 📌 Basic Syntax

grep [options] PATTERN [file...]

PATTERN → The text or regular expression to search.

file → File(s) in which to search.

options → Modify search behavior (case sensitivity, line numbers, etc.).

## 🚀 Common Examples

# 1️⃣ Search for a Word in a File
grep "error" logfile.txt


Finds all lines containing the word error.

# 2️⃣ Case-Insensitive Search
grep -i "error" logfile.txt

# 3️⃣ Search Recursively in Directories
grep -r "main" /etc


Searches inside all files under /etc.

# 4️⃣ Show Line Numbers
grep -n "root" /etc/passwd

# 5️⃣ Count Matches
grep -c "failed" auth.log


Outputs only the number of matching lines.

# 6️⃣ Invert Match (Show Lines Not Matching)
grep -v "success" logfile.txt

# 7️⃣ Match Whole Words
grep -w "root" /etc/passwd

# 8️⃣ Use Regex Patterns

Lines starting with ERROR:

grep "^ERROR" logfile.txt


Lines ending with .conf:

grep "\.conf$" files.txt

# 9️⃣ Search Multiple Patterns
grep -E "error|fail|critical" logfile.txt


Or use egrep (equivalent to grep -E).

# 🔄 Combine with Other Commands

Search running processes for nginx:

ps aux | grep nginx


Find IPs in logs:

cat access.log | grep -oE "[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+"

## 📂 Useful Options
Option	Description
-i	Case-insensitive search
-r	Recursive search
-n	Show line numbers
-c	Count matches
-v	Invert match (show non-matching lines)
-w	Match whole word
-o	Show only matching part of line
-l	List only filenames with matches
-E	Use extended regex (equivalent to egrep)
-A NUM	Show NUM lines after match
-B NUM	Show NUM lines before match
-C NUM	Show NUM lines around match

## ⚡ Practical Use Cases

Search for failed login attempts in logs:

grep "Failed password" /var/log/auth.log


Show all .conf lines in /etc:

grep -r "\.conf" /etc


Display lines around matches:

grep -C 3 "error" logfile.txt


Find email addresses:

grep -E "[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-z]{2,}" file.txt
