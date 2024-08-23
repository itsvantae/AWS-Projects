# Network Infrastructure Overview
Before diving into the actual deployment, it's essential to establish a strong foundation. This initial setup will serve as the backbone for our 3-tier application architecture, ensuring that everything runs smoothly and efficiently as we build out the rest of the system.

This base network consists of:

* A VPC.
* Two (2) public subnets spread across two availability zones (Web Tier).
* Two (2) private subnets spread across two availability zones (Application Tier).
* Two (2) private subnets spread across two availability zones (Database Tier).
* One (1) public route table that connects the public subnets to an internet gateway.
* One (1) private route table that will connect the Application Tier private subnets and a NAT gateway.

To kick off our project, head over to the AWS Management Console. Once there, navigate to the VPC console. Start by creating a new VPC. Choose the ‘VPC and more’ option, and name the project something relevant like ‘multi-tier-webApp.’ Set the CIDR block to 10.0.0.0/16 to define the IP address range for your VPC.






