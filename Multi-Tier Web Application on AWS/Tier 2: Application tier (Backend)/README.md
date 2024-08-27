# Application tier (Backend)
The Application Tier is essentially where the heart of our app resides. This is where the source code and core operations send and retrieve data to and from the Web and Database tiers.

The structure is very similar to the Web Tier but with some minor additions and considerations.

What we will build:

- A launch template to define the type of EC2 instances.
- An Auto Scaling Group (ASG) to dynamically provision EC2 instances.
- An Application Load Balancer (ALB) to route traffic from the Web tier.
- A Bastion host to securely connect to our application servers.

## 1. Create an application server launch template
This template will define the type of EC2 instances our backend services will use, so let’s create a new template named 'multiapp-appServer’.

We will use the same settings as the `brainiac-webServer-template` (Amazon Linux 2, t2.micro-1GB, and the same key pair).

The security group settings will differ since this is a private subnet where all our application source code will reside. We need to ensure it is not accessible from the outside.

We will allow ICMP–IPv4 from the `brainiac-webServer-sg` security group to enable pinging the application server from our web server.  
