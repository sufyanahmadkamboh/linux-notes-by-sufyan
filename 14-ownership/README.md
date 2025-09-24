# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 👤 File & Directory Ownership – `chown`, `chgrp`

In Linux, every file and directory has an **owner** and an associated **group**. Ownership defines **who can access or modify files**, together with permissions (`chmod`). The commands `chown` and `chgrp` are used to manage this ownership.

---

## 📌 Types of Ownership

1. **User (Owner)** → The person who created or owns the file.  
2. **Group** → A set of users who share access rights.  
3. **Others** → Everyone else on the system.  

You can check ownership with:

ls -l
-rw-r--r--  1 user group  1234 Sep 24 12:00 file.txt

user → Owner of the file

group → Group that owns the file

## 🔑 chown – Change File Owner

Basic Syntax
chown [OPTIONS] NEW_OWNER FILE

Examples

# Change owner to alice:

sudo chown alice file.txt


# Change both owner and group:

sudo chown alice:devs project.txt


(Owner = alice, Group = devs)

# Change owner for a directory (recursively):

sudo chown -R bob /var/www/html

## 👥 chgrp – Change Group Ownership
Basic Syntax
chgrp [OPTIONS] NEW_GROUP FILE

Examples

Change group to developers:

sudo chgrp developers file.txt


Change group recursively:

sudo chgrp -R devs /opt/projects

## 🔍 Checking Changes

After changing ownership, confirm with:

ls -l


Example output:

-rw-r--r--  1 alice devs  2048 Sep 24 14:00 project.txt


Owner is now alice

Group is now devs

## ✅ Try it Yourself

Task 1: Create a file test.txt and change its owner to another user on your system.

Task 2: Add a new group devteam, then assign a file to that group using chgrp.

Task 3: Recursively change the owner of a directory project/ to ubuntu.

Task 4: Verify changes using ls -l.