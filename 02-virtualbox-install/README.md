# Installation on VirtualBox

Steps

Download ISO (e.g., Ubuntu Server LTS).

Create VM in VirtualBox: 2 CPU, 2–4GB RAM, 20GB disk.

Attach ISO, start VM, follow installer.

After install, detach ISO; install Guest Additions if needed.

Try it

bash
Copy code
sudo apt update && sudo apt upgrade -y
hostnamectl
ip a
Common pitfalls

Enable virtualization in BIOS.

Use Bridged or NAT + Host-Only for connectivity.
