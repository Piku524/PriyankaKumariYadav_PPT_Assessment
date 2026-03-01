Task 10: VPC 3-Tier Architecture

Objective
Design a 3-tier network in AWS with public and private subnets to understand VPC, subnets, NAT Gateway, Internet Gateway, NACLs, and SSH tunneling.

## Architecture
- VPC CIDR: 10.0.0.0/24
- Public Subnet (Web Tier): 10.0.0.0/26
- Private Subnet (App Tier): 10.0.0.64/26
- Private Subnet (DB Tier): 10.0.0.128/26
- Internet Gateway attached to VPC
- NAT Gateway in Public Subnet for Internet access of private instances
- Security Groups configured for tier-based access
- NACLs configured for private subnet traffic control

## Steps Performed
1. Created VPC and subnets
2. Created and attached Internet Gateway
3. Configured public and private route tables
4. Created NAT Gateway and updated private route table
5. Launched EC2 instances in public and private subnets
6. Configured SSH tunneling for private instance access via public instance
7. Configured Network ACLs for private subnets
