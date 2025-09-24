# Linux Partitions and Filesystem

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

Linux storage is organized into **partitions** and **filesystems**. Understanding these is critical for installing, managing, and maintaining Linux systems.

---

## 📌 What Are Partitions?

A **partition** is a logical division of a physical hard disk. It defines how storage space is separated and used.  

In Linux, partitions are usually named like:
- `/dev/sda1` → First disk, first partition  
- `/dev/sda2` → First disk, second partition  
- `/dev/sdb1` → Second disk, first partition  

Linux does not use drive letters (like Windows `C:`, `D:`). Instead, everything is mounted under the **root (`/`) directory**.

---

## 📌 Common Linux Partitions

1. **Root (`/`)**  
   - The main partition.  
   - Contains the entire Linux system (binaries, configs, libraries).  
   - Minimum required partition for Linux installation.  
   - Recommended size: **20–50 GB** or more for servers.  

2. **Swap**  
   - Space on disk used when RAM is full.  
   - Works as virtual memory.  
   - Recommended size:  
     - RAM < 2 GB → swap = 2 × RAM  
     - RAM 2–8 GB → swap = same as RAM  
     - RAM > 8 GB → swap = 4–8 GB (depends on workload)  

3. **/home (Optional Separate Partition)**  
   - Stores user files, documents, and configurations.  
   - Keeping it separate ensures user data remains safe during OS reinstall.  

4. **/boot (Optional Separate Partition)**  
   - Holds bootloader (GRUB) and kernel images.  
   - Typically 500 MB – 1 GB.  

5. **/var (Optional Separate Partition)**  
   - Stores logs, caches, and databases.  
   - Useful for servers where logs grow large.  

6. **/tmp (Optional Separate Partition)**  
   - Stores temporary files.  
   - Helps in isolating temp space from filling the root partition.  

---

## 📌 Partition Table Types

1. **MBR (Master Boot Record)**  
   - Legacy format.  
   - Supports up to **4 primary partitions** (or 3 primary + 1 extended).  
   - Max disk size = 2 TB.  

2. **GPT (GUID Partition Table)**  
   - Modern standard (used with UEFI).  
   - Supports up to **128 partitions**.  
   - Handles disks larger than 2 TB.  
   - More robust (stores multiple copies of partition table).  

---

## 📌 Filesystems in Linux

A **filesystem** defines how files are stored, organized, and accessed on a partition.  

### 🔹 Common Filesystems

| Filesystem | Description | Use Case |
|------------|-------------|----------|
| **ext4** | Most widely used Linux filesystem, journaling support, stable | Default choice for desktops and servers |
| **xfs** | High-performance, scalable filesystem | Preferred in RHEL/CentOS for large systems |
| **btrfs** | Advanced features: snapshots, compression, copy-on-write | Used in SUSE/openSUSE, experimental in others |
| **ext3** | Older journaling filesystem (ext4 replaced it) | Legacy systems |
| **ext2** | Non-journaling filesystem | Useful for boot partitions |
| **zfs** | Advanced features: snapshots, replication, integrity checking | Storage servers, large datasets |
| **swap** | Not a filesystem, but partition type for virtual memory | Swap partitions/files |

---

## 📌 Checking Partitions and Filesystems


lsblk -f

## Shows block devices, partitions, and filesystems.

df -h


## Shows mounted filesystems and usage.

mount | column -t


## Displays currently mounted partitions.

blkid


## Shows UUIDs and filesystem types.

📌 Example Layout (Desktop/Server)
Disk: /dev/sda
├── /dev/sda1   → /boot   (1 GB, ext4)
├── /dev/sda2   → swap    (4 GB, swap)
├── /dev/sda3   → /       (40 GB, ext4)
└── /dev/sda4   → /home   (100 GB, ext4)

📌 Mount Points

Linux mounts partitions to directories.

Example: /dev/sda3 is mounted at /.

Configured in /etc/fstab for persistence.

Example /etc/fstab entry:

UUID=xxxx-xxxx  /       ext4  defaults  0 1
UUID=yyyy-yyyy  /home   ext4  defaults  0 2
UUID=zzzz-zzzz  swap    swap  defaults  0 0

## 📝 Summary

Partitions divide storage into logical sections.

Root (/) is mandatory, swap is highly recommended.

/home, /boot, /var can be separate partitions for flexibility.

MBR = legacy, GPT = modern and preferred.

Filesystems define how data is stored: ext4 (default), xfs (enterprise), btrfs (advanced).

Use tools like lsblk, df, and blkid to explore partitions.

## 📚 Next Steps

Practice listing partitions with lsblk and fdisk -l.

Try mounting and unmounting partitions manually.

Learn how to resize partitions and filesystems with gparted or lvextend.

Explore advanced filesystems like btrfs and zfs.