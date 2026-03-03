# TASK 4 — Hybrid Architecture Simulation (AWS)
## Objective
Simulate a secure hybrid architecture using:
- Bastion Host (Jump Server)
- Public Subnet
- Private Subnet
- Route Tables
- Security Groups
- Controlled SSH access

Traffic Flow:
User → Bastion Host → Private VM

---
## Architecture Overview

VPC CIDR: 10.0.0.0/16

Subnets:
- Public Subnet: 10.0.1.0/24
- Private Subnet: 10.0.2.0/24

Instances:
- Bastion Host (Public Subnet, Public IP enabled)
- Private VM (Private Subnet, No Public IP)
---
## Step 1: Create VPC and Subnets
- Created VPC with CIDR 10.0.0.0/16
- Created:
  - Public Subnet (10.0.1.0/24)
  - Private Subnet (10.0.2.0/24)
---
## Step 2: Create Internet Gateway
- Created Internet Gateway
- Attached it to the VPC
---
## Step 3: Configure Route Tables
### Public Route Table:
- Route: 0.0.0.0/0 → Internet Gateway
- Associated with Public Subnet
### Private Route Table:
- Route: 10.0.0.0/16 → local
- No route to Internet Gateway
- Associated with Private Subnet
This isolates the private subnet from the internet.

---
## Step 4: Launch Instances
### Bastion Host:
- Subnet: Public Subnet
- Public IP: Enabled
- Security Group:
  - SSH (22) allowed from My IP only

### Private VM:
- Subnet: Private Subnet
- Public IP: Disabled
- Security Group:
  - SSH (22) allowed only from Bastion Security Group
---

## Step 5: Configure Security Groups
Bastion Security Group:
- SSH (22) from My IP

Private VM Security Group:
- SSH (22) from Bastion Security Group only

This ensures only Bastion Host can access the Private VM.
---

## Step 6: Access Private VM using Bastion Host
### Connect to Bastion Host:
```bash
ssh -i Kiiy.pem ec2-user@<Bastion_Public_IP>
