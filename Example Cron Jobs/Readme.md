1. Run a backup script every day at 2 AM:

```
0 2 * * * /home/user/backup.sh
```

2. Clear logs every Sunday at midnight:

```
0 0 * * 0 rm -rf /var/log/*.log
```

3. Run a script every 5 minutes:

```
*/5 * * * * /home/user/check_disk.sh
```

4. Ping servers daily at 6 AM and log output:

```
0 6 * * * /home/user/ping_servers.sh >> /home/user/ping.log
```

5. 🔹 Useful Cron Commands
   View cron jobs:
   ```
   crontab -l
   ```

   Edit cron jobs:
   ```
   crontab -e
   ```

   Remove all cron jobs:
   ```
   crontab -r
   ```


1️⃣ Update system packages every day at 3 AM
```
0 3 * * * apt update && apt upgrade -y
```


2️⃣ Delete files older than 7 days from /tmp every midnight
```
0 0 * * * find /tmp -type f -mtime +7 -delete
```

3️⃣ Monitor memory usage every 30 minutes
```
*/30 * * * * free -h >> /var/log/memory_usage.log
```

4️⃣ Check disk usage hourly and alert if >80%
```
0 * * * * df -h | awk '$5+0 > 80 {print $0}' >> /var/log/disk_alerts.log
```


5️⃣ Restart a service (e.g., nginx) if it crashes
```
*/5 * * * * systemctl is-active --quiet nginx || systemctl restart nginx
```


6️⃣ Database backup every day at 1 AM
```
0 1 * * * mysqldump -u root -p'yourpassword' mydb > /backups/mydb_$(date +\%F).sql
```


7️⃣ Run a script only on weekdays (Mon–Fri) at 9 AM
```
0 9 * * 1-5 /home/user/daily_report.sh
```


8️⃣ Run a script on the first day of every month at midnight
```
0 0 1 * * /home/user/monthly_cleanup.sh
```


🔹 Useful Cron Management Commands

         List jobs for current user
         ```
         crontab -l
         ```
         
         Edit jobs for current user
         ```
         crontab -e
         ```
         Remove all jobs for current user
         ```
         crontab -r
         ```
         
         List jobs for another user (root only)
         ```
         crontab -u username -l
         ```
         
         View system-wide cron jobs
         ```
         cat /etc/crontab
         ls /etc/cron.d/
         ```
         
         Check cron service status
         ```
         systemctl status cron
         ```

📌 Day 3 — Cron Jobs Cheat Sheet
🔹 Cron Basics

Cron = Linux job scheduler (runs tasks automatically at given times).

Cron syntax:
```
* * * * * command_to_run
| | | | |
| | | | └── Day of week (0-6, Sun=0)
| | | └──── Month (1-12)
| | └────── Day of month (1-31)
| └──────── Hour (0-23)
└────────── Minute (0-59)
```



🔹 Cron Examples

✅ Every day at 2 AM
```
0 2 * * * /home/user/backup.sh
```

✅ Every Sunday at midnight
```
0 0 * * 0 rm -rf /var/log/*.log
```

✅ Every 5 minutes
```
*/5 * * * * /home/user/check_disk.sh
```

✅ Every 2 minutes
```
*/2 * * * * /home/user/script.sh
```

✅ Daily at 6 AM with logs
```
0 6 * * * /home/user/ping_servers.sh >> /home/user/ping.log
```

✅ Every 30 minutes — log memory usage
```
*/30 * * * * free -h >> /var/log/memory_usage.log
```

✅ Hourly disk usage check
```
0 * * * * df -h | awk '$5+0 > 80 {print $0}' >> /var/log/disk_alerts.log
```

✅ Restart nginx if it’s down (every 5 min)
```
*/5 * * * * systemctl is-active --quiet nginx || systemctl restart nginx
```

✅ Database backup daily at 1 AM
```
0 1 * * * mysqldump -u root -p'mypass' mydb > /backups/mydb_$(date +\%F).sql
```

✅ Run on weekdays at 9 AM (Mon–Fri)
```
0 9 * * 1-5 /home/user/daily_report.sh
```

✅ Run on 1st of each month at midnight
```
0 0 1 * * /home/user/monthly_cleanup.sh
```



🔹 Cron Management Commands

📋 List cron jobs (current user):
```
crontab -l
```

✏️ Edit cron jobs:
```
crontab -e
```

🗑 Remove all cron jobs:
```
crontab -r
```

👤 List jobs for another user (root only):
```
crontab -u username -l
```

📂 View system-wide cron jobs:
```
cat /etc/crontab
ls /etc/cron.d/
```

⚡ Check if cron service is running:
```
systemctl status cron
```




