
## **3️⃣ root-cause.md**

# Root Cause

The EC2 Security Group did not allow inbound traffic on port 80 (HTTP).  

- SSH and HTTPS were allowed, but HTTP requests from users could not reach the web server.  
- This caused the application to appear inaccessible, even though Nginx was running and healthy.