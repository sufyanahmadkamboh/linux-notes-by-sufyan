# cron Jobs


bash
Copy code
crontab -e
# m h dom mon dow command
0 3 * * * /usr/local/bin/backup.sh
crontab -l
