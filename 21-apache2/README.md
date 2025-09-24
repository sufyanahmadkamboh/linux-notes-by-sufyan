# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🌐 Apache2 Installation & Basics (Ubuntu)

Apache HTTP Server (**Apache2**) is one of the most popular and reliable open-source web servers. It is widely used for hosting websites, web apps, and APIs on Linux servers.  

This guide covers installation and basic usage of **Apache2 on Ubuntu**.

---

## 📌 Step 1: Update System

Always update your package lists before installation:

sudo apt update && sudo apt upgrade -y

## 📌 Step 2: Install Apache2

sudo apt install apache2 -y


Verify installation:

apache2 -v

## 📌 Step 3: Manage Apache2 Service

Start Apache:

sudo systemctl start apache2


Enable Apache on boot:

sudo systemctl enable apache2


Restart Apache:

sudo systemctl restart apache2


Check Apache status:

sudo systemctl status apache2

## 📌 Step 4: Verify Installation

Open a web browser and visit:

http://localhost


or, if on a remote server, use:

http://<your-server-ip>


You should see the default Apache welcome page.

## 📌 Step 5: Basic Apache Directories

Default Document Root: /var/www/html

Main Config File: /etc/apache2/apache2.conf

Virtual Hosts: /etc/apache2/sites-available/

Enabled Sites: /etc/apache2/sites-enabled/

Logs: /var/log/apache2/ (access.log, error.log)

## 📌 Step 6: Hosting a Website

Create a Test Page
echo "Hello from Apache on Ubuntu!" | sudo tee /var/www/html/index.html


Visit http://<server-ip> to see your custom page.

## 📌 Step 7: Virtual Hosts (Multiple Sites)

Create a new directory for your site:

sudo mkdir -p /var/www/mywebsite
sudo chown -R $USER:$USER /var/www/mywebsite


Create a sample page:

echo "<h1>Welcome to My Website</h1>" > /var/www/mywebsite/index.html


Create a new virtual host config:

sudo nano /etc/apache2/sites-available/mywebsite.conf


Add:

<VirtualHost *:80>
    ServerAdmin admin@mywebsite.com
    ServerName mywebsite.com
    ServerAlias www.mywebsite.com
    DocumentRoot /var/www/mywebsite
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>


Enable the site and reload:

sudo a2ensite mywebsite.conf
sudo systemctl reload apache2


Disable the default site (optional):

sudo a2dissite 000-default.conf
sudo systemctl reload apache2

## 📌 Step 8: Firewall Configuration (UFW)

Allow Apache traffic:

sudo ufw allow 'Apache Full'


Check rules:

sudo ufw status

## ✅ Try it Yourself

Install Apache2 on Ubuntu.

Replace the default index.html with your custom message.

Create a new virtual host for testsite.local.

Add a record in /etc/hosts (127.0.0.1 testsite.local) and test it.

Check logs in /var/log/apache2/.