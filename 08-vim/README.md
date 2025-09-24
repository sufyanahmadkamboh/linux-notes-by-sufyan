# Vim Editor

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

**Vim** (Vi IMproved) is a powerful text editor in Linux. It comes pre-installed on most distributions and is widely used by system administrators, developers, and DevOps engineers.  

Unlike simple editors (like `nano`), **Vim is modal**, meaning it works in different modes depending on what you want to do.

---

## 📌 Why Use Vim?

- Always available by default on most Linux systems.  
- Extremely fast and lightweight.  
- Supports syntax highlighting, search/replace, macros, plugins.  
- Perfect for editing configuration files, code, and scripts on servers.  

---

## 📌 Vim Modes

1. **Normal Mode (default)**  
   - Used for navigation and editing commands.  
   - Press `Esc` to return here.  

2. **Insert Mode**  
   - Used for typing text.  
   - Enter with `i`, `a`, or `o`.  

3. **Visual Mode**  
   - Used for selecting and manipulating text.  
   - Enter with `v` (character) or `V` (line).  

4. **Command-Line Mode**  
   - Used for saving, quitting, searching.  
   - Enter with `:` from Normal mode.  

---

## 📌 Starting Vim

vim filename.txt

If the file does not exist, Vim will create it.

If the file exists, it will open for editing.

## 📌 Basic Navigation

* h	Move left
* l	Move right
* k	Move up
* j	Move down
* 0	Jump to beginning of line
* $	Jump to end of line
* w	Jump forward one word
* b	Jump backward one word
* gg	Jump to beginning of file
* G	Jump to end of file
* :n	Go to line number n

## 📌 Insert Text

i	Insert before cursor
a	Insert after cursor
o	Insert new line below
O	Insert new line above
I	Insert at start of line
A	Insert at end of line

Press Esc to return to Normal mode.

## 📌 Editing Text

x	Delete character under cursor
dd	Delete current line
dw	Delete word
u	Undo last change
Ctrl + r	Redo
yy	Copy (yank) line
p	Paste after cursor
P	Paste before cursor
r<char>	Replace character
cw	Change word (delete + insert)

## 📌 Saving and Quitting

In Normal mode, press : to enter Command-Line mode:

:w	Save file (write)
:q	Quit
:wq	Save and quit
:x	Save and quit (same as :wq)
:q!	Quit without saving
:w filename	Save as another file

# 📌 Search and Replace

/word	Search for "word" forward
?word	Search for "word" backward
n	Repeat last search forward
N	Repeat last search backward
:%s/old/new/g	Replace all "old" with "new"
:%s/old/new/gc	Replace all with confirmation

## 📌 Visual Mode (Select & Edit)

v	Start character selection
V	Start line selection
y	Yank (copy) selection
d	Delete selection
>	Indent selection
<	Unindent selection

# 📌 Useful Tips

Line Numbers:

:set number


Syntax Highlighting:

:syntax on


Search Highlighting:

:set hlsearch


Disable Highlighting:

:nohlsearch


Open multiple files:

vim file1 file2
:n   # next file
:prev   # previous file

## 📌 Example Workflow

Open a file:

vim test.txt


Press i → enter Insert mode → type text.

Press Esc → return to Normal mode.

Save and quit:

:wq

## 📝 Summary

Vim has modes: Normal, Insert, Visual, Command.

Use i to insert, Esc to go back, :wq to save and quit.

Navigate with h j k l, delete with dd, copy with yy, paste with p.

Search with /pattern, replace with :%s/old/new/g.

Vim is lightweight, powerful, and always available on Linux.

