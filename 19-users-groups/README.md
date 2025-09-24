# Users & Groups


bash
Copy code
sudo adduser alice
sudo usermod -aG sudo alice
getent passwd alice
getent group sudo
sudo deluser alice --remove-home
