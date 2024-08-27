# Web tier (Frontend)
The Web Tier, also known as the ‘Presentation’ tier, is where users will interact with our application. This tier will host the web servers that deliver the frontend of our application to users.

Here's what we'll build:

- A web server launch template to define the specifications of the EC2 instances for the application.
- An Auto Scaling Group (ASG) to automatically adjust the number of EC2 instances based on demand.
- An Application Load Balancer (ALB) to efficiently distribute incoming traffic to the appropriate targets.

# 1. Create a web server launch template
Now it's time to create a launch template that our Auto Scaling Group (ASG) will use to dynamically launch EC2 instances in the public subnets.

In the EC2 console, go to ‘Launch templates’ under the ‘Instances’ menu. Create a new template named ‘multiapp-webserver’ with these settings:

- **AMI**: Amazon Linux 2
- **Instance type**: t2.micro (1GB – Free Tier)
- **Key pair**: New or existing
- **Security group**: New, with inbound rules for SSH, HTTP, and HTTPS
- **VPC**: Select the appropriate VPC you created earlier.

No need to specify subnets at this stage.

![now3](https://github.com/user-attachments/assets/8d9fab71-5258-4535-8de1-62af9f4bf990)

Under ‘Advanced details > User data,’ we need to paste in our script that installs an Apache web server and a basic HTML web page. You can view the specific script 




