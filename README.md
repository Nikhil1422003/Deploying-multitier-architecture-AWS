# Deploying-multitier-architecture-AWS
 Deploying A Multi-Tier Website Using AWS EC2

# Project Description

#### Project Title: Migration of Company ABC's Product to AWS with High Availability and Auto Scaling

# Objective:
- To migrate Company ABC's existing MySQL database and PHP website to AWS, ensuring high availability and scalability by leveraging Amazon EC2, Auto Scaling, and Amazon RDS services.

#### Components:
- **MySQL Database:** To be migrated to Amazon RDS for managed database services.
- **PHP Website:** To be hosted on Amazon EC2 instances with Auto Scaling for high availability.

#### Goals:
- Ensure high availability of the website by enabling Auto Scaling
- Migrate the MySQL database to Amazon RDS.
- Configure necessary security groups and network settings for seamless communication between EC2 instances and the RDS instance.

# Key Features of the Project

#### Scalable Computing Capacity:
- Utilizes Amazon EC2 instances to provide scalable computing capacity, allowing for dynamic adjustment based on traffic and resource requirements.

#### High Availability:
- Implements Auto Scaling to ensure the website remains highly available by maintaining a minimum of two instances at all times. This helps in handling traffic spikes and ensures reliability.

#### Managed Database Service:
- Migrates the MySQL database to Amazon RDS, offering automated backups, patching, and scalability, reducing the administrative burden on managing the database.

#### Automated Scaling:
- Configures Auto Scaling policies to automatically adjust the number of EC2 instances in response to traffic patterns, ensuring optimal performance and cost-efficiency.

#### Secure Networking:
- Sets up appropriate security groups and network configurations to allow secure communication between EC2 instances and the RDS instance, and to manage inbound and outbound traffic effectively.

#### Optimized Storage:
- Utilizes Amazon EBS (Elastic Block Store) for reliable and high-performance storage attached to EC2 instances.

#### Configuration Management:
- Provides a streamlined process to configure and modify the PHP website to use the new RDS database endpoint, ensuring seamless integration.

#### Step1.VPC SETUP
 **Creating VPC is better to secure our architecture safe**
- Create vpc and provide CIDR range ` 10.0.0.0/24 `
- Create subnets one for public and another for private
- Create internet gateway and attach
- Create route table then edit routes add IGW to the route table
- For public subnets click on subnet associations and add public subnet
- For private subnet click on subnet associations and add private subnet

#### Step2.Launch an EC2 Instance
- Select an Amazon Machine Image (AMI): Choose Amazon Linux 2 AMI.
- Select Instance Type: Choose ` t2.micro `
- Configure Instance: Ensure selection of the correct VPC.
- Add Storage: Default 8 GB is sufficient.
- Configure Security Group: Add rules for HTTP (port 80) and SSH (port 22).

####  Enable Auto Scaling
- Navigate to EC2 Dashboard.
- Auto Scaling Groups
- Create an Auto Scaling Group.
- Attach the previously created EC2 instance template.
- Configure group size: Minimum 2 instances.
- Set scaling policies to manage the desired capacity automatically.

**Connect to the ec2 instance previously created and update the machine and install apache2 commands given below**
```
sudo yum update
sudo yum install https -y
sudo systemctl start httpd service

```

