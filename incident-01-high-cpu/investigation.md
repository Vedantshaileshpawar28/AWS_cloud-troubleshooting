# Investigation

## Step 1: Check instance status
Since this is an EC2 instance, I would first verify that the instance is running:

```bash
aws ec2 describe-instances --filters "Name=tag:Name,Values=WebAppServer"

## Step 1: Check CPU usage
Simulate checking CPU usage on EC2:

```bash
top
## step 2 :Check running process 

ps aux --sort=-%cpu | head -n 10

## step 3 :Check recent deployments / cron jobs

ls -lrt /var/www/
crontab -l
 
## step 4 Check application logs for errors:


tail -n 100 /var/log/nginx/access.log
tail -n 100 /var/log/nginx/error.log
