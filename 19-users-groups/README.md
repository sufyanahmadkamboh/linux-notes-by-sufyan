# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 👥 Users and Groups in Linux

Linux is a **multi-user operating system**, meaning multiple people (or services) can use the system simultaneously.  
Managing **users and groups** is crucial for **security and access control**.

---

## 📌 Key Concepts

- **User** → An account that can log in or own processes/files.  
- **Group** → A collection of users that share permissions.  
- **Root user** → Superuser with full control.  
- **UID (User ID)** and **GID (Group ID)** → Numeric identifiers for users/groups.  

---

## 📂 Important Files

- `/etc/passwd` → Stores user account details.  
- `/etc/shadow` → Stores encrypted user passwords.  
- `/etc/group` → Stores group information.  

---

## 👤 User Management

### Add a New User

sudo adduser alice

or

sudo useradd -m alice

Set Password
sudo passwd alice

Delete a User
sudo deluser alice


or

sudo userdel -r alice


(-r removes home directory too).

## 👥 Group Management

Add a Group
sudo addgroup devs

Delete a Group
sudo delgroup devs

Add User to Group
sudo usermod -aG devs alice

Check Groups of a User
groups alice

## 🔑 Switching Users

Switch to Another User
su - alice

Run Command as Another User
sudo -u alice command

Switch to Root User
sudo -i

## 🔍 Viewing Users & Groups

Show Current User
whoami

Show All Logged-In Users
who

Show Detailed User Info
id alice


Output example:

uid=1001(alice) gid=1001(alice) groups=1001(alice),1002(devs)

## ✅ Try it Yourself

Create a user student and set a password.

Create a group trainers and add student to it.

Verify student’s groups using groups student.

Switch to student using su - student.

Delete the user and group.