# 📺 Linux Course on YouTube  
🎥 [Watch the full course here](https://youtu.be/tdxQ0O1qu9U?list=PLJB9b1bbB85HR7xXgpuWTibPWTprBEVi0)

---

# ⏰ Task Scheduling with `cron`

`cron` is a **time-based job scheduler** in Linux.  
It allows you to **automate repetitive tasks** such as running scripts, performing backups, clearing logs, or monitoring services.

---

## 📌 Key Files

- **`crontab`** → User-specific cron table (list of scheduled jobs).  
- **`/etc/crontab`** → System-wide cron table.  
- **`/etc/cron.d/`** → Directory for custom cron jobs.  
- **`/var/log/syslog`** → Location of cron logs (Debian/Ubuntu).  

---

## 📌 Crontab Syntax

Each cron job follows this format:

* * * * * command_to_run

| | | | |
| | | | +---- Day of the week (0-6, Sun=0)
| | | +------ Month (1-12)
| | +-------- Day of the month (1-31)
| +---------- Hour (0-23)
+------------ Minute (0-59)

yaml
Copy code

---

## 📊 Examples

### Edit Crontab

crontab -e
List Cron Jobs
bash
Copy code
crontab -l
Remove Cron Jobs
bash
Copy code
crontab -r
Common Cron Jobs
Run script every day at midnight:

bash
Copy code
0 0 * * * /home/user/backup.sh
Run command every 15 minutes:

bash
Copy code
*/15 * * * * /home/user/script.sh
Run every Monday at 5 AM:

bash
Copy code
0 5 * * 1 /usr/bin/python3 /home/user/report.py
Run every hour:

bash
Copy code
0 * * * * echo "Hourly check" >> /tmp/hourly.log
Run once at reboot:

bash
Copy code
@reboot /home/user/startup.sh

## 📌 Special Strings in Cron

Instead of numeric fields, cron supports shortcuts:

String	Meaning	Example
@reboot	Run once at startup	@reboot script.sh
@yearly	Run once a year (0 0 1 1 *)	@yearly backup.sh
@monthly	Run once a month (0 0 1 * *)	@monthly report.sh
@weekly	Run once a week (0 0 * * 0)	@weekly cleanup.sh
@daily	Run once a day (0 0 * * *)	@daily logrotate.sh
@hourly	Run once an hour (0 * * * *)	@hourly sync.sh

## 📌 Environment Variables in Cron

You can set environment variables inside a crontab file:

bash
Copy code
PATH=/usr/local/bin:/usr/bin:/bin
SHELL=/bin/bash
## 📂 Cron Logs
Check logs (Ubuntu/Debian):

bash
Copy code
grep CRON /var/log/syslog
On CentOS/RHEL:

bash
Copy code
sudo less /var/log/cron

## ✅ Try it Yourself

Create a cron job to log the date every 5 minutes into /tmp/date.log.

Schedule a Python script to run daily at 6 AM.

Use @reboot to start a script automatically after system startup.

Verify jobs with crontab -l and check logs.