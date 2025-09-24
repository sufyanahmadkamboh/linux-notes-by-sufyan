# Logs & journalctl


bash
Copy code
sudo tail -f /var/log/syslog
sudo journalctl -u nginx --since "1 hour ago"
sudo journalctl -xe
