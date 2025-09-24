# Firewall (ufw & iptables)

ufw

bash
Copy code
sudo ufw allow OpenSSH
sudo ufw allow 80,443/tcp
sudo ufw enable
sudo ufw status numbered
iptables (quick view)

bash
Copy code
sudo iptables -L -n -v
