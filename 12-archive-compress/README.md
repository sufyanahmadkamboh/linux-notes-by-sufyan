# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 📦 Archiving & Compression in Linux

Archiving and compression are essential for managing files and directories in Linux. They help you **bundle multiple files into a single archive** and **reduce file sizes** to save disk space or transfer faster over networks.

---

## 📌 Difference Between Archiving & Compression
- **Archiving** → Combining multiple files into one (without reducing size). Example: `tar`  
- **Compression** → Reducing file size using algorithms. Example: `gzip`, `bzip2`, `xz`  
- Together, we often **archive first, then compress** (e.g., `.tar.gz`)

---

## 🗂️ Common Tools
- `tar` → Archive multiple files into one `.tar` file  
- `gzip` / `gunzip` → Compress and decompress `.gz` files  
- `bzip2` / `bunzip2` → Higher compression than gzip (`.bz2`)  
- `xz` / `unxz` → Very high compression ratio (`.xz`)  
- `zip` / `unzip` → Archive + compress into `.zip` format (cross-platform)

---

## 🚀 Using `tar` (Archive Tool)

### Create an Archive

tar -cvf archive.tar file1 file2 dir1/

c → create

v → verbose (show progress)

f → filename

### Extract an Archive

tar -xvf archive.tar


x → extract

## Extract to a specific directory:

tar -xvf archive.tar -C /path/to/dir/

View Contents of Archive
tar -tvf archive.tar

## 🔽 Compression with tar + gzip

Create Compressed Archive (.tar.gz)
tar -czvf archive.tar.gz file1 file2 dir1/


z → gzip compression

Extract Compressed Archive
tar -xzvf archive.tar.gz

## 🔽 Compression with tar + bzip2

Create .tar.bz2
tar -cjvf archive.tar.bz2 file1 file2 dir1/


j → bzip2 compression

Extract .tar.bz2
tar -xjvf archive.tar.bz2

## 🔽 Compression with tar + xz
Create .tar.xz
tar -cJvf archive.tar.xz file1 file2 dir1/


J → xz compression

Extract .tar.xz
tar -xJvf archive.tar.xz

## 🔽 Using gzip Directly

Compress a File
gzip file.txt


(This creates file.txt.gz and removes the original file.)

Decompress
gunzip file.txt.gz


Keep the original file:

gzip -k file.txt

## 🔽 Using bzip2

bzip2 file.txt      # Creates file.txt.bz2
bunzip2 file.txt.bz2

## 🔽 Using xz

xz file.txt         # Creates file.txt.xz
unxz file.txt.xz

## 🔽 Using zip & unzip (Cross-platform)

Create a Zip Archive
zip archive.zip file1 file2 dir1/

Extract a Zip Archive
unzip archive.zip

## ✅ Try it Yourself

Task 1: Create an archive of /etc named etc.tar

Task 2: Compress a log file with gzip, then decompress it

Task 3: Create a .tar.gz of your home directory, extract it to /tmp/test

Task 4: Zip 3 text files into notes.zip, then unzip to a new folder