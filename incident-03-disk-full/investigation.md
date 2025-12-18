# Investigation

## Step 1: Check disk usage
```bash
df -h

Simulated Output:

Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      8G    8G    0   100% /
tmpfs           1G    0     1G  0% /dev/shm


Root filesystem at 100% usage.


## Step 2: Identify large files
du -sh /var/log/*


Simulated Output:

1.5G /var/log/nginx/access.log
800M /var/log/nginx/error.log
50M  /var/log/syslog


Large log files consuming most disk space.

##Step 3: Check application logs
tail -n 50 /var/log/nginx/error.log


Output shows normal logging; no recent crashes.

Issue is disk space, not application error.

##step 4 Step 4: Check log rotation
cat /etc/logrotate.conf


Observed log rotation not configured for Nginx logs.

Logs grew indefinitely, causing disk full.