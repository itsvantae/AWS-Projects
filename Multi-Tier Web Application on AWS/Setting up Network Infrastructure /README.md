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

To increase the availability of our Brainiac application, we’ll use two AZs (us-east-1a and us-east-1b), two public subnets, and four private subnets. We’ll add a NAT gateway later when we’re ready to build out the Application tier.

![1st](https://github.com/user-attachments/assets/1abf3010-b064-4fb5-aa03-bd8cfdca52f5)

![3d1](https://github.com/user-attachments/assets/a9dc4632-0adf-4be9-8bc1-dc35b03d89eb)

# Enable auto-assign IPv4
After creating all the necessary assets, make sure to enable the 'Auto-assign public IPv4 address' option for both public subnets and click save. This will allow you to access the resources in these subnets via the Internet.

![3d-3](https://github.com/user-attachments/assets/7981744b-663c-4a96-82ae-f71970a29d31)

# Set main route table
When the VPC is created, it comes with a default route table, known as the ‘main table.’ If you want your public route table (public-rtb) to act as the main table, go to the ‘Route tables’ section, select the public-rtb, and then choose ‘Set as main table’ from the ‘Actions’ dropdown menu. This will ensure that the public-rtb is used as the primary route table for your VPC.

![3d4](https://github.com/user-attachments/assets/1ce81f51-1195-4749-92bc-1231a6656be6)

# Create a NAT Gateway
A NAT gateway lets instances in private subnets connect to external resources and the Internet for tasks like updates. To ensure high availability, it's recommended to deploy two NAT gateways in public subnets (one in each availability zone). However, for now, we will deploy just one NAT gateway.

Navigate to ‘NAT Gateways’ and create a new gateway called public-NAT-1. Select one of the public subnets, allocate an elastic IP, and create the gateway.

![3d5](https://github.com/user-attachments/assets/dd6f2c0d-9200-4b98-928c-f7b1c828a0fa)

# Configure private route tables
When creating a VPC, four private route tables are automatically generated for each private subnet. However, we only need one private route table for the Application Tier subnets. To avoid confusion, it's important to use clear naming conventions. Let's go to the route tables section and organize them to keep things simple and easy to manage.

Select any one of the private route tables and adjust the name to something like ‘brainiac-webApp-rtb-private1.’ This will be our private route table. Now we can associate this table with all four private subnets (-subnet-private1, -subnet-private2, -subnet-private-3, -subnet-private4)

![3d6](https://github.com/user-attachments/assets/12fc7a18-7b9c-4e0f-b2c1-c6b370256ae1)

Now let’s add a new route to our NAT gateway. To update the route for a private subnet, select one of the private route tables, then click 'Edit routes.' Add the NAT gateway you previously created as the target for the destination route. This will allow the private subnet to access external resources through the NAT gateway.

![now](https://github.com/user-attachments/assets/4667c6aa-6ccb-44b4-9058-7cc45b0a0d95)

The extra route tables are not needed, so let's delete them. When you're done, you should have two route tables: one associated with two subnets and another associated with four subnets.

![3d10](https://github.com/user-attachments/assets/1ef9a44a-ccef-4d22-92ad-6f1c4ace4fbd)

Great job! Now that the foundation is set, we can move on to deploying resources like EC2 instances in each tier and configuring them to communicate with each other.























