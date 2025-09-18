🔹 1. Check Memory Usage
````
#!/bin/bash
# check_memory.sh
USAGE=$(free | grep Mem | awk '{print $3/$2 * 100.0}')
if (( ${USAGE%.*} > 80 )); then
  echo "CRITICAL: Memory usage is above 80%! ($USAGE%)"
else
  echo "Memory usage is normal ($USAGE%)"
fi
````
