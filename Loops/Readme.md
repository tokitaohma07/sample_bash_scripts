1️⃣ Check Memory Usage
```
#!/bin/bash
# check_memory.sh
USED=$(free -m | awk '/Mem:/ {print $3}')
TOTAL=$(free -m | awk '/Mem:/ {print $2}')
PERCENT=$(( USED * 100 / TOTAL ))

if [ $PERCENT -gt 80 ]; then
  echo "CRITICAL: Memory usage above 80% ($PERCENT%)"
else
  echo "Memory usage is normal ($PERCENT%)"
fi
```


2️⃣ Check CPU Load
```
#!/bin/bash
# check_cpu.sh
LOAD=$(uptime | awk -F'load average:' '{print $2}' | awk '{print $1}' | sed 's/,//')

if (( $(echo "$LOAD > 2.0" | bc -l) )); then
  echo "High CPU load: $LOAD"
else
  echo "CPU load is normal: $LOAD"
fi
```



3️⃣ Check Service Status
```
#!/bin/bash
# check_service.sh
SERVICE="ssh"

if systemctl is-active --quiet $SERVICE; then
  echo "$SERVICE is running"
else
  echo "$SERVICE is NOT running"
fi
```



4️⃣ Simple Backup Script
```
#!/bin/bash
# backup.sh
SRC="/home/user/data"
DEST="/home/user/backup"

mkdir -p $DEST
cp -r $SRC $DEST

echo "Backup completed from $SRC to $DEST"
```



5️⃣ Check Website Availability
```
#!/bin/bash
# check_website.sh
URL="https://example.com"
if curl -s --head $URL | grep "200 OK" > /dev/null; then
  echo "Website $URL is UP"
else
  echo "Website $URL is DOWN"
fi
```



