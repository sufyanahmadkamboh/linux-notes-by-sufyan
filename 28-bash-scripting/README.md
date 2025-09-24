# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🖥️ Bash Scripting Basics

**Bash** (Bourne Again SHell) is the most widely used shell in Linux.  
With Bash scripting, you can **automate tasks, run commands in sequence, build utilities, and simplify system administration**.

---

## 📌 Why Learn Bash Scripting?

- Automate repetitive tasks  
- Manage system backups, logs, and updates  
- Write deployment scripts for DevOps workflows  
- Create custom utilities for Linux servers  

---

## 📂 Creating Your First Script

1. Create a file:

nano hello.sh

Add:

#!/bin/bash
echo "Hello, World!"


Make it executable:

chmod +x hello.sh


Run:

./hello.sh

📌 Script Structure
#!/bin/bash
# This is a comment
# Author: Sufyan Ahmad

# Variables
NAME="Sufyan"

# Print message
echo "Hello $NAME"

# Conditional
if [ $NAME == "Sufyan" ]; then
    echo "Welcome, DevOps Engineer!"
else
    echo "Unknown User"
fi

## 📌 Variables

NAME="Linux"
echo "I am learning $NAME"


Environment variable:

echo $HOME


Read user input:

read USERNAME
echo "You entered: $USERNAME"

## 📌 Conditional Statements

if [ -f /etc/passwd ]; then
  echo "File exists"
else
  echo "File missing"
fi


Comparison operators:

-eq → equal

-ne → not equal

-lt → less than

-gt → greater than

-f → file exists

-d → directory exists

## 📌 Loops

For Loop
for i in 1 2 3 4 5; do
  echo "Number $i"
done

While Loop
count=1
while [ $count -le 5 ]; do
  echo "Count $count"
  ((count++))
done

## 📌 Functions

greet() {
  echo "Hello, $1!"
}

greet Sufyan
greet DevOps

## 📌 Exit Status

Every command returns an exit status (0 = success, non-zero = error).

ls /etc/passwd
echo $?   # 0 if success

## 📌 Scheduling Scripts with Cron

Run script daily at midnight:

0 0 * * * /home/user/backup.sh

## ✅ Try it Yourself

Write a script that prints today’s date and time.

Write a script that checks if a file exists, then prints a message.

Write a loop to print numbers 1–10.

Write a script that accepts a name as input and greets the user.

Automate your script with cron to run every hour.