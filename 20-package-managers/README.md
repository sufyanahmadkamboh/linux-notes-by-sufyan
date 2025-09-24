# Package Managers (apt, dnf, pacman)

Debian/Ubuntu (apt)

bash
Copy code
sudo apt update && sudo apt upgrade -y
sudo apt install -y nginx
RHEL/Alma (dnf/yum)

bash
Copy code
sudo dnf check-update
sudo dnf install -y nginx
Arch (pacman)

bash
Copy code
sudo pacman -Syu
sudo pacman -S nginx
