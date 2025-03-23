Objective
The goal of this project is to deploy a web application on an AWS EC2 instance with a web server (Apache/Nginx) and connect it to an AWS RDS MySQL/PostgreSQL database for data management.

Steps to Implement:
Create an EC2 Instance
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
•	Create a Subnet in the Availability Zone
•	Navigate to the VPC Console → Click on Subnets.
•	Click Create Subnet and select the VPC where the EC2 instance is running.
•	Assign an Availability Zone (e.g., us-east-1a).
•	Allocate an IP address range (CIDR block).
•	Click Create to launch Instance.

•	Create an RDS MySQL Database and Integrate it with EC2
•	Navigate to the AWS RDS Console.
•	Click Create Database and choose MySQL.
•	Select Standard Create and choose a DB instance type (db.t3.micro for free tier).
•	Under Connectivity, select: 
o	VPC: The same as the EC2 instance.
o	Subnet Group: Use the previously created subnet.
o	Public Access: Enable if the database needs to be accessed from outside AWS.
•	Create a new security group and allow MySQL port (3306).
•	Set a Master Username and Password for database access.
•	Click Create Database and wait for the status to become Available.

•	Connect to EC2 Using PuTTY

•	Open PuTTY: 
o	Enter EC2 Public IP under Host Name.
Install MySQL and Connect to the RDS Database

Update System

sudo apt update
Install MySQL Client

sudo apt install mysql-server -y
Start MySQL Service

sudo systemctl start mysql.service
Command to Connect the RDS MySQL Database

mysql -h database-mysql.ckhqewgcs9xu.us-east-1.rds.amazonaws.com -P 3306 -u admin -p

•	Replace database-mysql.ckhqewgcs9xu.us-east-1.rds.amazonaws.com with your actual RDS endpoint.
•	Enter the password when prompted.Then we can access the database.

Now we can access the RDS that created in server and create Tables and do necessary activites within RDS.

