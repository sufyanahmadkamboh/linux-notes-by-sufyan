# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 📦 Linux Package Managers

A **package manager** is a tool that automates the process of **installing, upgrading, configuring, and removing software** on Linux.  
Different Linux distributions use different package managers, but the concepts are similar.

---

## 📌 Why Use a Package Manager?

- Installs software with all required dependencies  
- Keeps software up-to-date  
- Ensures system stability and security  
- Provides easy removal/uninstallation  
- Manages software repositories  

---

## 🐧 Popular Package Managers by Distribution

| Distribution        | Package Manager | Commands Example |
|---------------------|-----------------|------------------|
| **Debian/Ubuntu**  | `apt`, `dpkg`   | `apt install nginx` |
| **RHEL/CentOS**    | `yum`, `dnf`, `rpm` | `yum install nginx` |
| **Fedora**         | `dnf`           | `dnf install nginx` |
| **Arch Linux**     | `pacman`        | `pacman -S nginx` |
| **OpenSUSE**       | `zypper`        | `zypper install nginx` |

---

## 🚀 Using `apt` (Debian/Ubuntu)

### Update Package Lists

sudo apt update

Upgrade Installed Packages
sudo apt upgrade -y

Install a Package
sudo apt install nginx -y

Remove a Package
sudo apt remove nginx

Search for a Package
apt search apache2

## 🚀 Using yum / dnf (RHEL, CentOS, Fedora)

Install a Package
sudo yum install nginx -y
# or
sudo dnf install nginx -y

Remove a Package
sudo yum remove nginx

Update Packages
sudo yum update -y

Search
yum search httpd

## 🚀 Using rpm (Low-level for RHEL/CentOS)

Install a Package File
sudo rpm -ivh package.rpm

Remove a Package
sudo rpm -e package_name

Query Installed Packages
rpm -qa | grep nginx

## 🚀 Using pacman (Arch Linux)

Update Repositories & Packages
sudo pacman -Syu

Install a Package
sudo pacman -S nginx

Remove a Package
sudo pacman -R nginx

## 🚀 Using zypper (OpenSUSE)

Install
sudo zypper install nginx

Remove
sudo zypper remove nginx

Update
sudo zypper update

## ✅ Try it Yourself

Update your system using the package manager for your distribution.

Install curl or wget and verify it with --version.

Search for nginx in repositories.

Remove a package you don’t need.

Check package history/logs.