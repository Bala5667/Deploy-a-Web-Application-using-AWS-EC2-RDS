Objective
The goal of this project is to deploy a web application on an AWS EC2 instance with a web server (Apache/Nginx) and connect it to an AWS RDS MySQL/PostgreSQL database for data management.

Steps to Implement:
1. Create an EC2 Instance
1.	Navigate to the AWS EC2 Console.
2.	Click on Launch Instance and choose Amazon Linux 2 or Ubuntu as the OS.
3.	Select an instance type (e.g., t2.micro for free tier).
4.	Configure network settings: 
o	Select a VPC and Subnet.
o	Ensure that Auto-assign Public IP is enabled.
5.	Add a Security Group: 
o	Allow SSH (Port 22) – For remote access.
o	Allow HTTP (Port 80) – To serve the website.
6.	Click on Launch and download the key pair (.pem file) for SSH access.
________________________________________
2. Create a Subnet in the Availability Zone
1.	Navigate to the VPC Console → Click on Subnets.
2.	Click Create Subnet and select the VPC where the EC2 instance is running.
3.	Assign an Availability Zone (e.g., us-east-1a).
4.	Allocate an IP address range (CIDR block).
5.	Click Create.
________________________________________
3. Create an RDS MySQL Database and Integrate it with EC2
1.	Navigate to the AWS RDS Console.
2.	Click Create Database and choose MySQL.
3.	Select Standard Create and choose a DB instance type (db.t3.micro for free tier).
4.	Under Connectivity, select: 
o	VPC: The same as the EC2 instance.
o	Subnet Group: Use the previously created subnet.
o	Public Access: Enable if the database needs to be accessed from outside AWS.
5.	Create a new security group and allow MySQL port (3306).
6.	Set a Master Username and Password for database access.
7.	Click Create Database and wait for the status to become Available.
________________________________________
4. Connect to EC2 Using PuTTY
1.	Download and install PuTTY.
2.	Convert the .pem key file to .ppk using PuTTYgen.
3.	Open PuTTY: 
o	Enter EC2 Public IP under Host Name.
o	Under SSH → Auth, upload the private key (.ppk).
4.	Click Open and login as ubuntu (for Ubuntu) or ec2-user (for Amazon Linux 2)
