# Web tier (Frontend)
The Web Tier, also known as the ‘Presentation’ tier, is where users will interact with our application. This tier will host the web servers that deliver the frontend of our application to users.

Here's what we'll build:

- A web server launch template to define the specifications of the EC2 instances for the application.
- An Auto Scaling Group (ASG) to automatically adjust the number of EC2 instances based on demand.
- An Application Load Balancer (ALB) to efficiently distribute incoming traffic to the appropriate targets.

## 1. Create a web server launch template
Now it's time to create a launch template that our Auto Scaling Group (ASG) will use to dynamically launch EC2 instances in the public subnets.

In the EC2 console, go to ‘Launch templates’ under the ‘Instances’ menu. Create a new template named ‘multiapp-webserver’ with these settings:

- **AMI**: Amazon Linux 2
- **Instance type**: t2.micro (1GB – Free Tier)
- **Key pair**: New or existing
- **Security group**: New, with inbound rules for SSH, HTTP, and HTTPS
- **VPC**: Select the appropriate VPC you created earlier.

No need to specify subnets at this stage.

![now3](https://github.com/user-attachments/assets/8d9fab71-5258-4535-8de1-62af9f4bf990)

Under ‘Advanced details > User data,’ we need to paste in our script that installs an Apache web server and a basic HTML web page. You can view the script [here](https://github.com/itsvantae/AWS-Projects/blob/main/Multi-Tier%20Web%20Application%20on%20AWS/Tier%201%3A%20Web%20tier%20(Frontend)/apache-install.sh) and click 'create launch template'.

## 2. Create an Auto scaling group (ASG)
To ensure high availability for the multi web app and minimize single points of failure, we'll create an Auto Scaling Group (ASG) that dynamically provisions EC2 instances across multiple Availability Zones in our public subnets.

Navigate to the ASG console from the sidebar menu and create a new group. Use the multiapp-webserver-template launch template that we set up earlier. Make sure to select the VPC along with both public subnets.

![3d12](https://github.com/user-attachments/assets/aef15893-2506-4a40-9e93-d883898c7d4a)

![3d13](https://github.com/user-attachments/assets/56d212f8-d001-4d68-88ee-31fe5c140fc1)

## 3. Application load balancer (ALB)
We'll set up an Application Load Balancer (ALB) to distribute incoming HTTP traffic to the appropriate EC2 instances. Name the ALB ‘brainiac-webServer-alb’ and make sure it's configured as ‘Internet-facing’ so it can handle HTTP/S requests from the web.








