# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# ⚙️ Linux `systemd` Basics

`systemd` is the **init system and service manager** used by most modern Linux distributions (Ubuntu, Debian, CentOS, Fedora).  
It is responsible for **booting the system, managing services, controlling processes, logs, and dependencies**.

---

## 📌 Key Features

- Parallel system startup for faster booting.  
- Manages services (`systemctl`) and logs (`journalctl`).  
- Handles dependencies between services.  
- Provides timers (alternative to cron).  
- Controls system states (shutdown, reboot, hibernate).  

---

## 📂 Important Directories

- `/etc/systemd/system/` → Custom unit files (preferred for user configs).  
- `/lib/systemd/system/` → Default system service files.  
- `/run/systemd/system/` → Runtime-generated units.  

---

## 🔑 Common `systemctl` Commands

### Service Management

Start a service:

sudo systemctl start nginx

Stop a service:

sudo systemctl stop nginx


Restart a service:

sudo systemctl restart nginx


Reload config without restarting:

sudo systemctl reload nginx


Check service status:

sudo systemctl status nginx

Enable/Disable Services

Enable service at boot:

sudo systemctl enable nginx


Disable service at boot:

sudo systemctl disable nginx


Check if enabled:

systemctl is-enabled nginx

System State Management

Reboot system:

sudo systemctl reboot


Power off:

sudo systemctl poweroff


Change to multi-user (CLI only) mode:

sudo systemctl isolate multi-user.target


Change to graphical mode:

sudo systemctl isolate graphical.target

## 📌 Managing Logs with journalctl

View all logs:

journalctl


View logs for a service:

journalctl -u nginx


Follow logs (like tail -f):

journalctl -u nginx -f


Show logs since boot:

journalctl -b

## 📌 Creating a Custom Service

Create a new service file:

sudo nano /etc/systemd/system/myapp.service


Add:

[Unit]
Description=My Custom App
After=network.target

[Service]
ExecStart=/usr/bin/python3 /home/user/myapp.py
Restart=always
User=ubuntu
Group=ubuntu

[Install]
WantedBy=multi-user.target


Reload systemd:

sudo systemctl daemon-reload


Start & enable service:

sudo systemctl start myapp
sudo systemctl enable myapp


Check logs:

journalctl -u myapp -f

## ✅ Try it Yourself

Start and stop the ssh or apache2 service.

Enable a service to start automatically at boot.

Create a small script (hello.sh) and run it as a custom systemd service.

Use journalctl -u <service> to view logs.