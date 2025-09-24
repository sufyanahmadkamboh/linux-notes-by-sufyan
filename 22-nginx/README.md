# Nginx Installation & Basics

Ubuntu

bash
Copy code
sudo apt update
sudo apt install -y nginx
sudo systemctl enable --now nginx
sudo ufw allow "Nginx Full"
Server block

bash
Copy code
sudo tee /etc/nginx/sites-available/example <<'CONF'
server {
  listen 80;
  server_name example.com;
  root /var/www/example;
  index index.html;
  location / {
    try_files $uri $uri/ =404;
  }
}
CONF
sudo ln -s /etc/nginx/sites-available/example /etc/nginx/sites-enabled/
sudo nginx -t && sudo systemctl reload nginx
Logs: /var/log/nginx/
