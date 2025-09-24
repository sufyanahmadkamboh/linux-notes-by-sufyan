# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔗 Soft Links vs Hard Links in Linux

Linux supports two types of links: **Soft (symbolic)** and **Hard** links.  
Links are pointers that allow multiple references to the same file, making file management more flexible.

---

## 📌 What is an Inode?

Every file in Linux is represented by an **inode** (index node).  
- **Inode stores metadata**: permissions, owner, size, disk blocks, etc.  
- File **name** is just a pointer to an inode.  

Links are simply **different names pointing to the same inode or data**.

---

## 🔗 Hard Links

- A **hard link** is another name for the same file (same inode).  
- Both original file and hard link point to the **same data blocks**.  
- If you delete the original file, the hard link still works (data exists until all links are deleted).  
- Can only be created **within the same filesystem/partition**.  

### Create Hard Link

ln file1.txt hardlink1.txt

Check Inode Numbers
ls -li


Both files will have the same inode number.

## 🔗 Soft Links (Symbolic Links)

A soft link (symlink) is like a shortcut (similar to Windows shortcuts).

It points to the original file by name/path, not by inode.

If the original file is deleted, the symlink becomes a broken link.

Can link across different filesystems/partitions.

Useful for creating shortcuts or redirection paths.

Create Soft Link
ln -s file1.txt softlink1.txt

Check Links
ls -l


Soft links will show with -> pointing to the original file:

lrwxrwxrwx  1 user group   8 Sep 24 15:00 softlink1.txt -> file1.txt

## 📊 Comparison: Hard Links vs Soft Links

Feature	Hard Link	Soft Link (Symbolic)
Points to	Inode (actual data)	File name/path
Inode number	Same as original	Different
Works across filesystems	❌ No	✅ Yes
If original deleted	Still works (data intact)	Broken link
Can link directories	❌ Not usually	✅ Yes
Size	Same size as original	Very small (just stores path)
✅ Examples
Create a File
echo "Hello Linux" > file1.txt

Hard Link
ln file1.txt hard1.txt
ls -li


Both files have the same inode and content.

Soft Link
ln -s file1.txt soft1.txt
ls -l


Soft link points to file1.txt.

Delete original file:

rm file1.txt
cat hard1.txt   # ✅ Works
cat soft1.txt   # ❌ Broken link

## ✅ Try it Yourself

Create a file data.txt.

Make a hard link hard.txt and a soft link soft.txt.

Compare their inode numbers using ls -li.

Delete data.txt and check which links still work.

Try making a soft link across directories.