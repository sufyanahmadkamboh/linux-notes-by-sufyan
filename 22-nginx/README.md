# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# ⚡ Nginx Installation & Basics (Ubuntu)

**Nginx** (pronounced *Engine-X*) is a high-performance web server, reverse proxy, and load balancer.  
It is known for **speed, scalability, and low resource usage**, making it ideal for modern web applications.

---

## 📌 Step 1: Update System

sudo apt update && sudo apt upgrade -y

## 📌 Step 2: Install Nginx

sudo apt install nginx -y


Verify installation:

nginx -v

## 📌 Step 3: Manage Nginx Service

Start Nginx:

sudo systemctl start nginx


Enable on boot:

sudo systemctl enable nginx


Restart Nginx:

sudo systemctl restart nginx


Check status:

sudo systemctl status nginx

## 📌 Step 4: Verify Installation

Open in browser:

http://localhost


or:

http://<your-server-ip>


You should see the Nginx welcome page.

## 📌 Step 5: Firewall Configuration (UFW)

Allow HTTP (port 80) and HTTPS (port 443):

sudo ufw allow 'Nginx Full'


Check rules:

sudo ufw status

## 📌 Step 6: Important Directories

Default Document Root: /var/www/html

Main Config File: /etc/nginx/nginx.conf

Server Blocks (Virtual Hosts): /etc/nginx/sites-available/

Enabled Sites: /etc/nginx/sites-enabled/

Logs: /var/log/nginx/ (access.log, error.log)

## 📌 Step 7: Hosting a Website

Create Web Root
sudo mkdir -p /var/www/mywebsite
sudo chown -R $USER:$USER /var/www/mywebsite

Create Index Page
echo "<h1>Welcome to My Nginx Site</h1>" > /var/www/mywebsite/index.html

Create Server Block
sudo nano /etc/nginx/sites-available/mywebsite


Add:

server {
    listen 80;
    server_name mywebsite.com www.mywebsite.com;

    root /var/www/mywebsite;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}


Enable site:

sudo ln -s /etc/nginx/sites-available/mywebsite /etc/nginx/sites-enabled/


Test config:

sudo nginx -t


Reload Nginx:

sudo systemctl reload nginx

## 📌 Step 8: Check Logs

Access log:

tail -f /var/log/nginx/access.log


Error log:

tail -f /var/log/nginx/error.log

## ✅ Try it Yourself

Install Nginx and confirm with the welcome page.

Create a new site testsite.local and configure a server block.

Update /etc/hosts with 127.0.0.1 testsite.local and test it.

Check access/error logs while visiting the site.

Disable the default site by removing the symlink in sites-enabled/.