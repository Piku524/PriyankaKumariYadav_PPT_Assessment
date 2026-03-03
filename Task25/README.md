Task: Multi-AZ Highly Available Web Application (AWS)

OBJECTIVE:
Deploy a fault-tolerant and highly available web application using:
VPC, EC2, Application Load Balancer (ALB), Auto Scaling Group (ASG), S3, and CloudWatch.

ARCHITECTURE OVERVIEW:

User
↓
Application Load Balancer (Public Subnets)
↓
Auto Scaling Group (EC2 in Private Subnets)
↓
S3 (Website Files)
CloudWatch (Monitoring)

STEPS PERFORMED:

Created a VPC with CIDR block 10.0.0.0/16.

Created four subnets:

Public-Subnet-1 (10.0.1.0/24)

Public-Subnet-2 (10.0.2.0/24)

Private-Subnet-1 (10.0.3.0/24)

Private-Subnet-2 (10.0.4.0/24)

Created and attached an Internet Gateway to the VPC.

Configured Route Tables:

Public Route Table connected to Internet Gateway.

Private Route Table connected to NAT Gateway.

Created a NAT Gateway in the public subnet for private subnet internet access.

Created Security Groups:

ALB-SG allows HTTP (port 80) from anywhere.

EC2-SG allows HTTP (port 80) only from ALB-SG.

Created a Launch Template with the following User Data script:

#!/bin/bash
yum update -y
yum install -y httpd awscli
systemctl start httpd
systemctl enable httpd
aws s3 sync s3://b220 /var/www/html

Created a Target Group with protocol HTTP and port 80.

Created an Application Load Balancer in public subnets and attached it to the target group.

Created an Auto Scaling Group:

Minimum capacity = 2

Desired capacity = 2

Maximum capacity = 4

Attached to target group

Created an S3 bucket named b220 and uploaded website files (index.html).

Created a CloudWatch alarm:

Metric: CPUUtilization

Threshold: greater than 70% for 5 minutes.

TESTING:
The application was accessed using the Application Load Balancer DNS name:
http://myalb-659451638.ap-south-1.elb.amazonaws.com/

Refreshing the page shows different hostnames, proving:

Load balancing

Multi-AZ deployment

High availability

RESULT:
High availability achieved
Fault tolerant architecture implemented
Auto Scaling enabled
Website served from S3 via EC2
Monitoring enabled using CloudWatch

CONCLUSION:
This project demonstrates a real-world highly available web application architecture using services from Amazon Web Services such as VPC, EC2, Application Load Balancer, Auto Scaling Group, S3, and CloudWatch.
