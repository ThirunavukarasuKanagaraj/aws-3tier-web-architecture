# aws-3tier-web-architecture
Designed and deployed a secure AWS 3-Tier Web Application Architecture using VPC, public/private subnets, Bastion Host, Web Server, App Server, and MariaDB RDS. Configured NAT Gateway, Internet Gateway, Route Tables, and Security Groups to enable secure communication between application layers. 
**Architecture Components**
   -Amazon VPC
   -Public and Private Subnets
   -Bastion Host
   -Web Server
   -App Server
   -Amazon RDS (MariaDB)
   -NAT Gateway
   -Internet Gateway
   -Route Tables
   -Security Groups
**Architecture Diagram**
<img width="971" height="601" alt="Tier3Topology" src="https://github.com/user-attachments/assets/33714cd4-5143-4f7a-873f-ce77a5a8d756" />
**AWS Services Used**
   ---Amazon EC2
   ---Amazon RDS
   ---Amazon VPC
   ---NAT Gateway
   ---Internet Gateway
   ---Route Tables
   ---Security Groups
**Project Objectives**
   ---Create a secure 3-tier architecture in AWS
   ---Implement public and private subnet isolation
   ---Configure secure SSH access using Bastion Host
   ---Deploy Apache Web Server and MariaDB services
   ---Enable secure communication between application layers
   ---Configure routing and security using AWS networking services
**Implementation Steps**
1. **VPC and Networking**
   ---Created custom VPC with CIDR block
   ---Configured public and private subnets
   ---Attached Internet Gateway to VPC
   ---Created NAT Gateway for private subnet internet access
   ---Configured Route Tables and subnet associations
2. **Security Configuration**
   ---Created Security Groups for:
   ---Bastion Host
   ---Web Server
   ---App Server
   ---Database Server
   ---Configured inbound and outbound traffic rules
3. **EC2 Deployment**
   ---Launched Bastion Host in public subnet
   ---Deployed Web Server with Apache installation using User Data
   ---Deployed App Server with MariaDB client configuration
4.** Database Setup**
   ---Created Amazon RDS MariaDB instance
   ---Configured DB subnet group
   ---Enabled secure database access from App Server
5.** Connectivity Testing**
   ---Connected to private instances through Bastion Host
   ---Verified communication between Web, App, and Database layers
**User Data Script - Web Server**
   #!/bin/bash
  sudo yum update -y
  sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
  sudo yum install -y httpd
  sudo systemctl start httpd
  sudo systemctl enable httpd
**User Data Script - App Server**
  #!/bin/bash
  sudo yum install -y mariadb-server
  sudo service mariadb start
   
Elastic IP
Amazon Linux 2
