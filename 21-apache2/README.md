# Apache2 Installation & Basics

Ubuntu

bash
Copy code
sudo apt update
sudo apt install -y apache2
sudo systemctl enable --now apache2
sudo ufw allow "Apache Full"
Sites

bash
Copy code
sudo a2ensite mysite.conf
sudo a2dissite 000-default.conf
sudo systemctl reload apache2
Logs: /var/log/apache2/
