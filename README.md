Objective
The goal of this project is to deploy a web application on an AWS EC2 instance with a web server (Apache/Nginx) and connect it to an AWS RDS MySQL/PostgreSQL database for data management.

Steps to Implement:
1. Create an EC2 Instance
•	Navigate to the AWS EC2 Console.
•	Click on Launch Instance and choose Amazon Linux 2 or Ubuntu as the OS.
•	Select an instance type (e.g., t2.micro for free tier).
•	Configure network settings: 
o	Select a VPC and Subnet.
o	Ensure that Auto-assign Public IP is enabled.
•	Add a Security Group: 
o	Allow SSH (Port 22) – For remote access.
o	Allow HTTP (Port 80) – To serve the website.
•	Click on Launch and download the key pair (.pem file) for SSH access.

