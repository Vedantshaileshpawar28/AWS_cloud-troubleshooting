# Resolution

1. Add inbound rule to allow HTTP (port 80) traffic:
```bash
aws ec2 authorize-security-group-ingress --group-id sg-0123456789abcdef0 --protocol tcp --port 80 --cidr 0.0.0.0/0

Retest connectivity:

curl http://54.123.45.67