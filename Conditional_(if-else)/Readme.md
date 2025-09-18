🔹 1. Check Memory Usage
```
#!/bin/bash
# check_memory.sh
USAGE=$(free | grep Mem | awk '{print $3/$2 * 100.0}')
if (( ${USAGE%.*} > 80 )); then
  echo "CRITICAL: Memory usage is above 80%! ($USAGE%)"
else
  echo "Memory usage is normal ($USAGE%)"
fi
```



🔹 2. Check CPU Load
```
#!/bin/bash
# check_cpu.sh
LOAD=$(uptime | awk -F'load average:' '{print $2}' | cut -d, -f1 | sed 's/ //')
if (( ${LOAD%.*} > 4 )); then
  echo "CRITICAL: CPU load is too high! ($LOAD)"
else
  echo "CPU load is normal ($LOAD)"
fi
```



🔹 3. Check if a Process is Running
```
#!/bin/bash
# check_process.sh
PROCESS="nginx"
if pgrep -x "$PROCESS" > /dev/null; then
  echo "Process $PROCESS is running."
else
  echo "Process $PROCESS is NOT running!"
fi
```



🔹 4. Backup a File
```
#!/bin/bash
# backup_file.sh
SOURCE="/etc/hosts"
DEST="/tmp/hosts.backup"
cp $SOURCE $DEST
echo "Backup of $SOURCE created at $DEST"
```



🔹 5. Check Logged-in Users
```
#!/bin/bash
# check_users.sh
COUNT=$(who | wc -l)
echo "There are $COUNT users logged in."
```



✅ These are small utility scripts, each teaching one useful concept:

Example 1 → memory check

Example 2 → CPU load

Example 3 → process check

Example 4 → file backup

Example 5 → logged-in users
