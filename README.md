# AWS SSH Honeypot with Cowrie

## Overview
This project deploys an **AWS-based SSH honeypot** using **Cowrie**, capturing unauthorized login attempts for analysis. It mimics an SSH server to log attacker behavior.

## Deployment Steps
1️. Launch an AWS EC2 instance 
   - Ubuntu 22.04, `t2.micro` (free-tier eligible).  
   - Open **port 2222** (for Cowrie) and restrict **port 22** (real SSH).  

2️. Install Docker & Cowrie on EC2 
   ```bash
   sudo apt update && sudo apt install -y docker.io
   sudo docker run -d --name cowrie -p 2222:2222 cowrie/cowrie
