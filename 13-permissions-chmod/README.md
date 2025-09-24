# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔑 File Permissions – `chmod`

Linux is a **multi-user operating system**, and file permissions are crucial to control **who can read, write, or execute** files. The `chmod` command is used to **change permissions** on files and directories.

---

## 📌 Types of Permissions

| Symbol | Name       | Description                          |
|--------|------------|--------------------------------------|
| `r`    | Read       | View contents of a file/directory    |
| `w`    | Write      | Modify a file / add or delete inside a directory |
| `x`    | Execute    | Run a file as a program / enter a directory |

---

## 👥 User Categories

| Symbol | Category        | Description                 |
|--------|-----------------|-----------------------------|
| `u`    | User (Owner)    | The owner of the file        |
| `g`    | Group           | Members of the file’s group |
| `o`    | Others          | Everyone else               |
| `a`    | All             | u + g + o                   |

---

## 🔍 Viewing Permissions

Use `ls -l` to see permissions:

ls -l
-rw-r--r--  1 user group  1234 Sep 24 12:00 file.txt

Breakdown of -rw-r--r--:

- → Regular file

rw- → User (owner) has read & write

r-- → Group has read only

r-- → Others have read only

## ✨ Using chmod

# 1️⃣ Symbolic Method

Grant execute permission to user:

chmod u+x script.sh


Remove write permission from group:

chmod g-w file.txt


Give read to others:

chmod o+r notes.txt


Give read/write/execute to all:

chmod a+rwx file.txt

# 2️⃣ Numeric (Octal) Method

Each permission has a value:

r = 4, w = 2, x = 1

Add them up for each user category:

Number	Permission
7	rwx
6	rw-
5	r-x
4	r--
0	---

Examples:

chmod 755 script.sh


User: 7 (rwx)

Group: 5 (r-x)

Others: 5 (r-x)

chmod 644 file.txt


User: 6 (rw-)

Group: 4 (r--)

Others: 4 (r--)

## 📂 Directory Permissions

r → List directory contents

w → Add/remove files in directory

x → Enter (cd) into directory

Example:

chmod 700 private/


Only the owner can access.

## ✅ Try it Yourself

Task 1: Create a file test.sh and set it executable only for you (700).

Task 2: Change a file’s permission to 644 and check with ls -l.

Task 3: Give a group execute access on a directory.

Task 4: Remove all permissions from a file and try to read it.