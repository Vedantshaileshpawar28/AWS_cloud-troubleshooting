# Root Cause

Log files in `/var/log/nginx/` grew without rotation or cleanup.  

- Disk space was completely consumed (100% full), preventing the application from writing new logs.  
- Lack of log rotation configuration caused the uncontrolled growth.