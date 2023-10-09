# Cloud-Hemo-Sphere-CSE472-Project
Cloud Hemo-Sphere is an online cloud service that manages blood donation groups and aims to increase accessibility and efficiency for blood banking in Bangladesh.

# How To Run
Download the .zip file.

## Local Installation using xampp and phpMyAdmin 
1. Create a database named bbdms in phpMyAdmin and import .sql file in SQL File folder
3. Copy extracted .zip folder to C:\xampp\htdocs
4. Connect to local host and use file path to run the application (e.g http://localhost/bbdms/index.php)

## Cloud Installation using Amazon Web Services
1. Create a VPC with desired CIDR block
2. Create at least two subnets (one public and one private) or if auto-scaling, at least three subnets (two public and one private)
3. Public subnets routed directly to internet gateway
4. Private subnet routed through NAT gateway to internet gateway
5. Create private Ubuntu EC2 instance for private subnet
6. Copy the contents in 'ubuntu scripts/Private Server Script.docx' in User Data or use the commands stepwise in SSH client terminal (latter is recommended as mysql commands may not run properly)
7. Create public Ubuntu EC2 instance for each public subnet
6. Copy the contents in 'ubuntu scripts/Public Server Script.docx' in User Data or use the commands stepwise in SSH client terminal (Make sure to change the DB Host IP address to private IP address of private server)
8. Using the given public IPv4 address should allow access to the web application
9. (Optional) Create a launch template of the public servers (through adding the public server script in user data) and add load balancers and auto-scaling for more functionality
