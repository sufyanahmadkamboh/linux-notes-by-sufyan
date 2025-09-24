# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# 📑 Logs & Monitoring with `journalctl` and Log Files

Logs are critical for **troubleshooting, auditing, and monitoring** a Linux system.  
They record system events, application errors, authentication attempts, and more.

---

## 📌 Where Logs are Stored

Most logs are stored in:

/var/log/


Common log files:
- `/var/log/syslog` → General system messages (Debian/Ubuntu)  
- `/var/log/messages` → General logs (RHEL/CentOS)  
- `/var/log/auth.log` → Authentication & security logs  
- `/var/log/kern.log` → Kernel logs  
- `/var/log/dpkg.log` → Package installations (Debian)  
- `/var/log/yum.log` → Package installations (RHEL/CentOS)  
- `/var/log/apache2/` → Apache web server logs  
- `/var/log/nginx/` → Nginx web server logs  

---

## 📌 Viewing Logs with `cat`, `less`, `tail`

- View entire log file:

bash
cat /var/log/syslog


Scroll logs:

less /var/log/syslog


Watch logs in real time:

tail -f /var/log/syslog


Show last 50 lines:

tail -n 50 /var/log/auth.log

## 📌 Using journalctl (systemd Logs)

journalctl reads logs managed by systemd journal.

Basic Usage
journalctl

Show Logs for Current Boot
journalctl -b

Follow Logs (like tail -f)
journalctl -f

Show Logs for a Specific Service
journalctl -u ssh
journalctl -u nginx

Show Logs Since a Time
journalctl --since "2024-09-01 10:00:00"
journalctl --since "1 hour ago"

Show Logs by Priority

Emergency (0)

Alert (1)

Critical (2)

Error (3)

Warning (4)

Notice (5)

Info (6)

Debug (7)

Example:

journalctl -p err -b


(Shows errors since boot)

## 📌 Rotating Logs

Logs can grow large over time. Linux uses logrotate to manage log rotation.

Config: /etc/logrotate.conf and /etc/logrotate.d/

Rotate manually:

sudo logrotate -f /etc/logrotate.conf

## ✅ Try it Yourself

Check the last 20 lines of /var/log/auth.log.

Watch system logs in real-time with tail -f /var/log/syslog.

Use journalctl -u ssh -f while connecting via SSH.

Find all error messages since last boot.

Explore Apache or Nginx logs in /var/log/.