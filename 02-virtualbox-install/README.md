# Install Linux on VirtualBox

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

This guide will help you set up a Linux distribution (such as **Ubuntu**, **Debian**, or **CentOS**) inside **Oracle VM VirtualBox** on your computer. VirtualBox allows you to create virtual machines (VMs) and run multiple operating systems on top of your existing OS.

---

## 📌 Why Use VirtualBox?

- Run Linux without replacing your current operating system.  
- Safe sandbox environment for experiments and learning.  
- Test networking, servers, and DevOps tools locally.  
- Easy snapshots → rollback anytime.  

---

## 🛠️ Prerequisites

1. **Host System**:  
   - Windows, macOS, or Linux PC with at least **8 GB RAM** and **50 GB free disk space** recommended.  

2. **Software Downloads**:  
   - [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
   - Linux ISO file (e.g. [Ubuntu ISO](https://ubuntu.com/download/desktop))  

3. **Optional** (Recommended):  
   - [VirtualBox Extension Pack](https://www.virtualbox.org/wiki/Downloads) → adds USB 2.0/3.0, RDP, etc.  

---

## 🚀 Step 1: Install VirtualBox

1. Download the installer for your host OS (Windows, macOS, or Linux).  
2. Run the installer and accept default options.  
3. After installation, open **Oracle VM VirtualBox Manager**.  

---

## 🚀 Step 2: Create a New Virtual Machine

1. Click **New** in VirtualBox Manager.  
2. Enter a **Name** (e.g. `Ubuntu-VM`).  
3. Select **Type** = Linux.  
4. Choose the correct **Version**:
   - Ubuntu (64-bit)  
   - Debian (64-bit)  
   - Red Hat / CentOS (64-bit)  

---

## ⚙️ Step 3: Configure VM Resources

- **Memory (RAM):**  
  - Minimum: 2 GB  
  - Recommended: 4 GB or more  

- **Processors (CPU):**  
  - Assign at least 2 cores if available.  

- **Hard Disk:**  
  - Create a new virtual hard disk.  
  - Size: 25–50 GB (VDI format, Dynamically Allocated).  

---

## 📂 Step 4: Mount Linux ISO

1. Select your VM → **Settings**.  
2. Go to **Storage**.  
3. Under *Controller: IDE* → choose **Empty Disk**.  
4. Click the disk icon → **Choose a disk file**.  
5. Select your downloaded Linux ISO file (e.g., `ubuntu-22.04.iso`).  

---

## 🚀 Step 5: Start the VM & Install Linux

1. Click **Start** to boot from the ISO.  
2. Follow the Linux installer steps:
   - Choose **Install Ubuntu/Debian/CentOS**.  
   - Select **Language** and **Keyboard Layout**.  
   - Configure **Time Zone**.  
   - Partition disk → choose **Erase disk and install** (only affects the VM).  
   - Set **Username** and **Password**.  

3. After installation finishes, reboot the VM.  
   - If asked to *remove installation media*, just unmount the ISO.  

---

## 🔄 Step 6: Post-Installation Setup

- **Update System Packages**:
  ```bash
  sudo apt update && sudo apt upgrade -y   # For Ubuntu/Debian

