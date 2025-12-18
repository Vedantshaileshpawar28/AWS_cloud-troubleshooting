# Investigation

## Step 1: Verify EC2 instance and application status
```bash
aws ec2 describe-instances --filters "Name=tag:Name,Values=WebAppServer"

Simulated Output: Instance running with public IP 54.123.45.67(example)
##step 2 
sudo systemctl status nginx

    Simulated Output: Nginx running

##step 3  check connectivity from internet

curl http://54.123.45.67

##Step 4: Check Security Group rules
aws ec2 describe-security-groups --group-ids sg-0123456789abcdef0

Simulated Output:

Inbound Rules:
- TCP 22 (SSH) 0.0.0.0/0
- TCP 443 (HTTPS) 0.0.0.0/0
# No TCP 80 (HTTP) rule


Observed that port 80 is missing, which prevents HTTP access.

##Step 5: Check local firewall (simulated)
sudo ufw status


Output: Firewall allows all traffic (no issue locally)