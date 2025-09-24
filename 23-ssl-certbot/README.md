# SSL Certificate with Certbot

Pre-req: DNS A record points to your server.

Nginx (Ubuntu)

bash
Copy code
sudo apt install -y certbot python3-certbot-nginx
sudo certbot --nginx -d example.com -d www.example.com
sudo systemctl status certbot.timer
Apache

bash
Copy code
sudo apt install -y certbot python3-certbot-apache
sudo certbot --apache -d example.com
Renewal

bash
Copy code
sudo certbot renew --dry-run
