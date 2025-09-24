# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 📝 Nano Editor – Complete Guide

Nano is a **simple, user-friendly text editor** that comes pre-installed in most Linux distributions. It is lightweight, easy to use, and perfect for beginners who want to edit files quickly without dealing with complex editors like Vim or Emacs.

---

## 📌 Features of Nano
- Simple and intuitive interface  
- Keyboard shortcuts displayed at the bottom of the screen  
- Syntax highlighting (in most versions)  
- Search and replace functionality  
- Supports cut, copy, and paste  
- Works directly inside the terminal  

---

## ⚙️ Installing Nano
Most Linux distributions already include Nano. To check if it’s installed:

nano --version

If not installed:

On Debian/Ubuntu:

sudo apt update && sudo apt install nano -y


On CentOS/RHEL:

sudo yum install nano -y


On Fedora:

sudo dnf install nano -y

## 🚀 Opening Files with Nano

To create or open a file:

nano filename.txt


If the file doesn’t exist, Nano will create it upon saving.

## ⌨️ Basic Keyboard Shortcuts in Nano

Nano uses control key combinations (shown as ^ on the bottom menu).
Here are the most useful ones:

Shortcut	Action
Ctrl + O	Write (save) file
Ctrl + X	Exit nano
Ctrl + R	Insert another file into current one
Ctrl + K	Cut selected text
Ctrl + U	Paste text
Ctrl + W	Search text
Ctrl + \	Search and replace
Ctrl + G	Help menu
Ctrl + C	Show cursor position (line/column)
Alt + A	Start selecting text
Alt + 6	Copy selected text

## 🔍 Searching in Nano

To search for a word:

Press Ctrl + W

Type the search term and press Enter

## 🔄 Search & Replace in Nano

Press Ctrl + \

Enter the search term and press Enter

Enter the replacement word and press Enter

Confirm each replacement with Y or skip with N

## 💾 Saving and Exiting

Save changes: Ctrl + O → press Enter

Exit Nano: Ctrl + X

If changes are unsaved, Nano will ask to save before exiting

## 🎨 Enabling Syntax Highlighting

Nano supports syntax highlighting via configuration files usually located at:

/usr/share/nano/*.nanorc


To enable them, edit your ~/.nanorc file:

include /usr/share/nano/*.nanorc

## 🧑‍💻 Why Use Nano?

Perfect for quick edits inside servers

Beginner-friendly

No steep learning curve

Pre-installed on most Linux systems