AWS SSH Honeypot with Cowrie (TrapShell)

Overview: This project sets up an AWS-based SSH honeypot using Cowrie, a medium-interaction honeypot that mimics an SSH server to log unauthorized access attempts. It allows for security monitoring and attacker behavior analysis.

Deployment Steps:

Launch an AWS EC2 Instance

Use Ubuntu 22.04 (t2.micro).
Open port 2222 (for Cowrie honeypot).
Restrict port 22 (real SSH) to your IP only.
--------------------------------------------
Install Docker & Cowrie on EC2:

sudo apt update && sudo apt install -y docker.io sudo docker run -d --name cowrie -p 2222:2222 cowrie/cowrie
--------------------------------------------
Monitor SSH Attack Attempts: 

sudo docker logs -f cowrie
--------------------------------------------
Analyze Logs 

sudo docker exec -it cowrie cat /cowrie/log/cowrie.log
--------------------------------------------

Sample Logs:

2025-03-15T22:51:21 Unauthorized SSH login attempt from 192.168.1.20 as 'root' 2025-03-15T22:52:10 Unauthorized SSH login attempt from 103.57.23.81 as 'admin'
--------------------------------------------



By: Eduardo Paz (https://github.com/PazEdu)
