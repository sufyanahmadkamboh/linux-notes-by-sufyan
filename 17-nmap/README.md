# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🌐 Network Scanning with `nmap`

`nmap` (Network Mapper) is a powerful open-source tool for **network discovery and security auditing**. It can be used to identify **live hosts, open ports, running services, operating systems**, and even detect vulnerabilities.

---

## 📌 Installation

On **Debian/Ubuntu**:

sudo apt update && sudo apt install nmap -y

## 📌 Basic Syntax

nmap [options] target


target → IP, hostname, or network range (e.g., 192.168.1.0/24)

options → Flags to control scanning behavior

## 🚀 Common Usage Examples

# 1️⃣ Scan a Single Host
nmap 192.168.1.10

# 2️⃣ Scan a Range of IPs
nmap 192.168.1.1-50

# 3️⃣ Scan an Entire Subnet
nmap 192.168.1.0/24

# 4️⃣ Host Discovery (Ping Scan)
nmap -sn 192.168.1.0/24


Lists live hosts without scanning ports.

## 🔑 Port Scanning

Scan Specific Port
nmap -p 22 192.168.1.10

Scan Multiple Ports
nmap -p 22,80,443 192.168.1.10

Scan Port Range
nmap -p 1-1000 192.168.1.10

Scan Top 1000 Ports (Default)
nmap target.com

## 🛠️ Service & Version Detection
nmap -sV 192.168.1.10


Identifies services and versions running on open ports.

## 🖥️ OS Detection
sudo nmap -O 192.168.1.10

## 🔍 Aggressive Scan (OS + Version + Script + Traceroute)
sudo nmap -A 192.168.1.10

## 📜 Saving Results

Save to text file:

nmap -oN scan_results.txt 192.168.1.10


Save to XML:

nmap -oX scan_results.xml 192.168.1.10

## 🔥 Advanced Examples

Scan Without DNS Resolution
nmap -n 192.168.1.10

Fast Scan (Top 100 Ports)
nmap -F 192.168.1.10

Stealth SYN Scan (Requires root)
sudo nmap -sS 192.168.1.10

UDP Scan
sudo nmap -sU 192.168.1.10

## ✅ Try it Yourself

Task 1: Discover all live hosts in your local subnet.

Task 2: Scan open ports of a web server (-p 1-1000).

Task 3: Detect services and versions running on your machine.

Task 4: Run an aggressive scan (-A) against a test server.