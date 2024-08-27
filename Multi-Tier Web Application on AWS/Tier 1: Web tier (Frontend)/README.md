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

![3d14](https://github.com/user-attachments/assets/b3ca5ed3-9cc7-4409-9340-a08854b503e1)

Note: Creating an ALB From the ASG interface automatically attaches the default security group to our ALB. We need the multiapp-webServer-sg, so after the ASG is complete, we need to go back to the load balancer and make sure the proper security group is attached.

The ALB needs to ‘listen’ over HTTP on port 80 and a target group that routes to our EC2 instances.

![now1](https://github.com/user-attachments/assets/04efddc4-49ff-441e-b927-012e50f7c1d7)

We’ll also add a dynamic scaling policy that tells the ASG when to scale up or down EC2 instances. For this build, we’ll monitor the CPU usage and create more instances when the usage is above 50% (feel free to use whatever metric is appropriate for your application).

![3d15](https://github.com/user-attachments/assets/f40b0716-0ff2-445d-884f-bb64ff43497f)

![3d16](https://github.com/user-attachments/assets/4155a618-f89b-452c-973c-bca5958e2950)

### Group size
Set the Auto Scaling Group (ASG) to provision the following:

- **Desired capacity**: 2 instances
- **Minimum capacity**: 2 instances
- **Maximum capacity**: 5 instances

![3d17](https://github.com/user-attachments/assets/ffdcc463-03e7-4151-9262-41bf218f23e1)

Review the settings and create the ASG. Once it's fully initialized, check the EC2 dashboard to see that two instances have been launched.

To verify that the ALB is routing traffic correctly, visit its public DNS. You should be able to access the website set up during the EC2 launch template creation.

![now2](https://github.com/user-attachments/assets/f049e3e1-341e-45b4-af15-3e58f48c6eb2)

## SSH
Let's confirm that we can SSH into our EC2 instance.

![now3](https://github.com/user-attachments/assets/d5700492-2eab-4e1f-96c3-61cda5b04f9c)

Success! We connected to two of the public subnets successfully and are progressing with the remaining tasks as outlined in the given input. Remember, this is the ‘Presentation’ layer, where our users will directly interact with our app.

















