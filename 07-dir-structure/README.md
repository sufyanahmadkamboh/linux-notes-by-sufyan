# Linux Directory Structure

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

When installing Linux, you will often see **partitions** such as `/`, `/home`, `/boot`, and `swap`. After installation, the **directory structure** (folders under `/`) follows the **Filesystem Hierarchy Standard (FHS)**.  

This guide explains both **partitions** and **directory structure** in detail.

---

## 📌 What Are Linux Partitions?

A partition is a division of your hard disk into sections that the OS uses for storing data. Unlike Windows, Linux uses a **single root (`/`) hierarchy** instead of drive letters (`C:`, `D:`).  

Key partitions:

1. **`/` (Root Partition)**  
   - The main partition that contains the entire Linux filesystem.  
   - Every file and directory starts from `/`.  
   - Minimum required for any Linux installation.  

2. **`swap` (Swap Space)**  
   - Acts as an overflow for RAM.  
   - If your system runs out of physical memory, inactive pages are moved to swap.  
   - Can be a partition or a swap file.  
   - Recommended size:  
     - RAM < 2 GB → swap = 2 × RAM  
     - RAM 2–8 GB → swap = RAM  
     - RAM > 8 GB → swap = 4–8 GB (depending on use case)  

3. **`/home` (Optional Separate Partition)**  
   - Stores user files, documents, downloads, and personal configurations.  
   - Useful to keep separate so user data is safe during OS reinstallation.  

4. **`/boot` (Optional Separate Partition)**  
   - Contains bootloader files (GRUB) and kernel images.  
   - Usually 500 MB – 1 GB in size.  
   - Helpful for troubleshooting dual-boot or encrypted setups.  

---

## 📌 Linux Directory Structure

After installation, Linux organizes everything into a **tree-like directory structure** under `/` (root).  

### 🗂️ Key Directories and Their Purpose

| Directory | Description |
|-----------|-------------|
| `/` | The **root** directory — top of the hierarchy. All other directories are inside `/`. |
| `/bin` | Essential user binaries (e.g., `ls`, `cat`, `cp`). Available in single-user mode. |
| `/sbin` | Essential system binaries (e.g., `fdisk`, `reboot`). For administrators (root). |
| `/boot` | Bootloader files, kernel images, and initrd. System boot happens from here. |
| `/dev` | Device files (e.g., hard drives as `/dev/sda`, USBs as `/dev/sdb`). |
| `/etc` | Configuration files for the system and installed software. |
| `/home` | User home directories (e.g., `/home/alice`, `/home/bob`). |
| `/lib`, `/lib64` | Shared libraries needed by system binaries and kernel modules. |
| `/media` | Mount point for removable devices (USB, DVD). |
| `/mnt` | Temporary mount point for filesystems (manual mounting). |
| `/opt` | Optional software installed manually (outside package manager). |
| `/proc` | Virtual filesystem providing process and kernel info (e.g., `/proc/cpuinfo`). |
| `/root` | Home directory for the **root user**. |
| `/run` | Runtime process information (PID files, sockets). Cleared at boot. |
| `/srv` | Data for services (e.g., web server files). |
| `/sys` | Kernel and hardware info (similar to `/proc`). |
| `/tmp` | Temporary files. Usually cleared on reboot. |
| `/usr` | Secondary hierarchy for user applications and files. |
| `/usr/bin` | Non-essential user binaries (applications installed by package manager). |
| `/usr/sbin` | Non-essential system binaries (admin tools). |
| `/usr/lib` | Libraries for `/usr/bin` and `/usr/sbin`. |
| `/usr/local` | Locally compiled software (user-installed, not from distro repos). |
| `/var` | Variable data: logs, caches, mail, print spool, databases. |
| `/var/log` | System and application logs. |
| `/var/tmp` | Temporary files preserved between reboots. |
