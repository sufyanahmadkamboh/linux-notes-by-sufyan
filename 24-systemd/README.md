# systemd Basics


bash
Copy code
systemctl status nginx
sudo systemctl enable --now myapp.service
journalctl -u myapp -f
Unit example: /etc/systemd/system/myapp.service

ini
Copy code
[Unit]
Description=My App

[Service]
ExecStart=/usr/local/bin/myapp
Restart=on-failure

[Install]
WantedBy=multi-user.target
