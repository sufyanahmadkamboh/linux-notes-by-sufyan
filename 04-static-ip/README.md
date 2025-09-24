# Static IP Setup

Netplan (Ubuntu) example: /etc/netplan/01-static.yaml

yaml
Copy code
network:
  version: 2
  ethernets:
    enp0s3:
      addresses: [192.168.56.10/24]
      gateway4: 192.168.56.1
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]
Apply:

bash
Copy code
sudo netplan apply
Verify

bash
Copy code
ip a
ip r
ping -c2 8.8.8.8
