# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔥 Firewall Management in Linux – `ufw` & `iptables`

A **firewall** controls incoming and outgoing network traffic based on rules.  
In Linux, two common tools are:

- **UFW (Uncomplicated Firewall)** → Beginner-friendly, easy to use.  
- **iptables** → Advanced, flexible packet filtering framework.  

---

## 📌 UFW – Uncomplicated Firewall

### Install UFW (if not installed)

sudo apt install ufw -y

Enable UFW
sudo ufw enable

Disable UFW
sudo ufw disable

Common UFW Commands

Allow SSH (port 22):

sudo ufw allow 22


Allow HTTP (80) and HTTPS (443):

sudo ufw allow 80
sudo ufw allow 443


Allow by service name:

sudo ufw allow 'Nginx Full'


Deny a port:

sudo ufw deny 21


Delete a rule:

sudo ufw delete allow 22


Show status with rules:

sudo ufw status verbose

## 📌 iptables – Advanced Firewall

iptables provides fine-grained control over network packets.
It uses chains (rules lists) inside tables.

Tables

filter → Default, handles ACCEPT/DROP rules.

nat → Network address translation (port forwarding).

mangle → Packet modification.

Chains

INPUT → Incoming traffic.

OUTPUT → Outgoing traffic.

FORWARD → Routed packets.

Common iptables Commands

View current rules:

sudo iptables -L -v -n


Allow incoming SSH:

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT


Allow HTTP/HTTPS:

sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT


Drop all incoming traffic (default deny policy):

sudo iptables -P INPUT DROP


Allow established/related connections:

sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT


Delete a rule:

sudo iptables -D INPUT -p tcp --dport 22 -j ACCEPT

Save iptables Rules (Persistent)

On Ubuntu/Debian:

sudo apt install iptables-persistent -y
sudo netfilter-persistent save


On CentOS/RHEL:

service iptables save

## ✅ Try it Yourself

Enable UFW and allow only SSH + HTTP traffic.

Block port 21 (FTP) using UFW.

List iptables rules with iptables -L -v -n.

Add a rule to allow HTTPS traffic in iptables.

Drop all other traffic except SSH and HTTP/HTTPS.