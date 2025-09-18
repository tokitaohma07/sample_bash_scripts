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
