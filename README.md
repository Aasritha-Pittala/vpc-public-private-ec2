# Project 3 – VPC with Public and Private Subnets + EC2 Instances

## Overview
In this project, I designed and deployed a Virtual Private Cloud (VPC) on AWS with both public and private subnets. I launched EC2 instances in each subnet to understand network segmentation, routing, and security. This setup helped me gain hands-on experience with AWS networking, routing tables, security groups, and private/public instance management.

---

## Services and Tools Used
- Amazon VPC
- EC2 Instances
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups
- AWS Management Console

---

## What I Did

### 1. Created a Custom VPC
I created a new VPC with a CIDR block `10.0.0.0/16`. This allowed me to have multiple subnets and control IP addressing within my network.

---

### 2. Created Public and Private Subnets
I created:
- **Public Subnet:** `10.0.1.0/24` → for resources accessible from the internet  
- **Private Subnet:** `10.0.2.0/24` → for internal resources, not directly accessible from the internet  

I ensured that the public subnet is associated with a route to the Internet Gateway, and the private subnet uses a NAT Gateway for outbound internet access if needed.

---

### 3. Configured Route Tables
I created two route tables:
- **Public Route Table:** Associated with the public subnet and routed `0.0.0.0/0` to the Internet Gateway  
- **Private Route Table:** Associated with the private subnet, routed `0.0.0.0/0` to the NAT Gateway for internet-bound traffic  

This allowed proper routing for instances in each subnet.

---

### 4. Launched EC2 Instances
I launched EC2 instances in each subnet:
- **Public EC2:** Accessible via SSH from my IP and had a public IP  
- **Private EC2:** Accessible only via the public EC2 (bastion host) or VPN  

I applied security groups to control inbound/outbound traffic for each instance.

---

### 5. Verified Connectivity
I tested connectivity:
- **Public EC2:** Accessible via SSH from my local machine  
- **Private EC2:** SSH access through the public EC2 (bastion)  
- Ensured that private EC2 could access the internet via NAT Gateway  

This confirmed that the VPC and subnet configuration worked as expected.

---

## Outcome
Through this project, I successfully:
- Created a secure and segmented VPC with public and private subnets  
- Launched and configured EC2 instances in both subnets  
- Set up routing, Internet Gateway, and NAT Gateway for proper connectivity  
- Tested and verified network access according to best practices

---

## Key Learnings
- AWS VPC design and architecture  
- Public vs private subnet use cases  
- Routing tables and gateways (IGW and NAT)  
- Security group configuration  
- Bastion host concept for accessing private instances  

---

## Author
Your Name
