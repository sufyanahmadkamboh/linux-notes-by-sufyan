# Setting Up a Static IP in Linux (VirtualBox VM)

🎥 **Watch the full Linux Course on YouTube** → [Click Here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

When running Linux inside VirtualBox, the default network setting is usually **DHCP** (Dynamic IP). This means your VM’s IP address can change after every reboot, which is a problem if you want to SSH consistently or run services.  

To fix this, you can configure a **Static IP Address**. This ensures your VM always uses the same IP.

---

## 📌 Why Use a Static IP?

- Consistent **SSH access** (no need to check IP each time).  
- Required for hosting services (web servers, databases, etc.).  
- Useful for **multi-VM labs** (Kubernetes, Ansible, Docker Swarm).  
- Prevents issues when DHCP assigns a new IP.  

---

## 🛠️ Step 1: Check Current Network

Open a terminal in your VM and run:

## Check interface name and current IP
ip a

## Check default gateway
ip r

## Check DNS servers
cat /etc/resolv.conf

Example findings:

Interface: enp0s3

Current IP: 192.168.1.120

Gateway: 192.168.1.1

DNS: 8.8.8.8

## 🛠️ Step 2: Plan Your Static IP

Must be in the same subnet as your host (e.g., 192.168.1.x).

Avoid conflicts → pick an unused IP.

Stay outside the router’s DHCP pool if possible.

Example: if DHCP range is 192.168.1.100–200, choose 192.168.1.220.

## ⚙️ Step 3: Configure Static IP

🔹 Ubuntu/Debian (Netplan)

Edit the netplan file:

sudo nano /etc/netplan/01-netcfg.yaml


(File name may also be 50-cloud-init.yaml)

## Add this config (adjust for your network):

network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.1.220/24
      gateway4: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]


## Apply changes:

sudo netplan apply


## Verify:

ip a
ping -c 4 google.com


## If using Bridged Adapter, your VM will also be reachable from other devices on your LAN.

## 📝 Summary

Use ip a and ip r to check your current setup.

Pick a free IP in the same subnet.

Configure via Netplan (Ubuntu/Debian) or ifcfg (RHEL/CentOS).

Test with ping and ssh.

## 📝 Note: A full walkthrough is available in the YouTube Course

