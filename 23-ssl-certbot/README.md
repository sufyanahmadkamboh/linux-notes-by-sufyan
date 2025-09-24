# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 🔒 SSL Certificate Setup with Certbot (Let’s Encrypt)

Securing websites with **HTTPS** is essential for privacy, security, and SEO.  
[Let’s Encrypt](https://letsencrypt.org/) provides **free SSL/TLS certificates**, and **Certbot** automates installation and renewal.

This guide explains how to enable HTTPS on your site using **Certbot** with Apache or Nginx on Ubuntu.

---

## 📌 Step 1: Prerequisites

- A **domain name** (e.g., `example.com`) pointing to your server’s IP.  
- A web server installed (Apache2 or Nginx).  
- Ports **80 (HTTP)** and **443 (HTTPS)** open in firewall.  

---

## 📌 Step 2: Install Certbot

Update system and install Certbot:

sudo apt update
sudo apt install certbot python3-certbot-apache -y   # For Apache
sudo apt install certbot python3-certbot-nginx -y    # For Nginx

## 📌 Step 3: Obtain SSL Certificate

For Apache:
sudo certbot --apache

For Nginx:
sudo certbot --nginx


Follow the prompts:

Enter your email address.

Agree to the terms.

Select your domain(s).

Choose whether to redirect HTTP → HTTPS.

## 📌 Step 4: Verify HTTPS

Visit:

https://your-domain.com


You should see a padlock icon in the browser.

## 📌 Step 5: Auto Renewal

Let’s Encrypt certificates are valid for 90 days.
Certbot installs a cron job/systemd timer for automatic renewal.

Test renewal:

sudo certbot renew --dry-run

## 📌 Step 6: Useful Commands

Check certificate status:

sudo certbot certificates


Manually renew:

sudo certbot renew


Renew and reload Apache/Nginx:

sudo systemctl reload apache2    # Apache
sudo systemctl reload nginx      # Nginx

## ✅ Try it Yourself

Install Apache or Nginx on Ubuntu.

Configure a domain name to point to your server.

Run certbot --apache or certbot --nginx to install SSL.

Test HTTPS in your browser.

Run certbot renew --dry-run to confirm auto-renewal.