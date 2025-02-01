# Web_App_Deploy
The aim of this project is to automate the deployment of a website using a Bash script. 
The steps below describe the process followed to deploy the website.
Log into AWS Management Console
Search for EC2
Click on EC2
Click on Instances
Click on Launch Instances
Instance name = Demo_WebApp
AMI = Ubuntu
Instance type = t2.micro
Assign Security Group to the instance
Assign Key Pair
Bash script provided in the user data box:
```#!/bin/bash
apt update -y && apt upgrade -y
apt install -y nginx
rm -f /var/www/html/index.nginx-debian.html
git clone https://github.com/Balotu/Web_App_Deploy.git /var/www/html
chown -R www-data:www-data /var/www/html
chmod -R 755 /var/www/html
systemctl restart nginx
systemctl enable nginx
```
Link to deployed website:
http://3.238.220.121/#first
This site was built using [HTML5 UP](https://html5up.net/)
