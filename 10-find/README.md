# find Command


bash
Copy code
find /var/log -type f -name "*.log" -size +10M
find . -type f -mtime -1 -print
find . -type f -exec grep -H "ERROR" {} \;
Safety: test with -print before -delete.
