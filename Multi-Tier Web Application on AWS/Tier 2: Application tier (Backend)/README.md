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

We will use the same settings as the 'multiapp-webserver' (Amazon Linux 2, t2.micro-1GB, and the same key pair).

The security group settings will differ since this is a private subnet where all our application source code will reside. We need to ensure it is not accessible from the outside.

We will allow ICMP–IPv4 from the 'multiapp-webServer-sg' security group to enable pinging the application server from our web server.  

![now](https://github.com/user-attachments/assets/83269051-412a-45aa-8197-801d603096d0)

The application servers will eventually need to access the database, so we need to make sure the mySQL package is installed on each instance.

In the ‘User data’ field under ‘Advanced details,’ paste in this script:

```
#!/bin/bash
sudo yum install mysql -y
```
Review and create the template.

## 2. Create an Auto Scaling Group (ASG)
Similar to the Web Tier, we’ll create an ASG from the brainiac-appServer-template called, ‘appServer-asg’.

Make sure to select the appropriate vpc and the 2 private subnets (subnet-private1 and subnet-private2).

![3d23](https://github.com/user-attachments/assets/aeff5016-3e4c-48c2-9508-e41918388a49)

## 3. Application Load Balancer (ALB)
Now we’ll create another ALB to route traffic from the Web Tier to the Application Tier. Name it to your convinience.

This ALB will be set to ‘Internal,’ since it will route traffic from our Web Tier rather than from the Internet.

![101](https://github.com/user-attachments/assets/ff7547a2-16a6-4afe-8474-a2b583d056c2)

We’ll also create another target group that will target our appServer EC2 instances. Now we can review our settings and create the group.

![3d26](https://github.com/user-attachments/assets/b891e672-748d-4811-bb16-9772ffad6a87)

Great! We should see two more EC2 instances running from our private subnets.

## Confirm connectivity from the Web Tier
Our application servers are up and running. Let’s verify connectivity by pinging the application server from one of the web servers.

SSH into one of the web server EC2 instances and ping the private IP address of an application server EC2 instance.

```ping PRIVATE_IPV4_ADDRESS```

If successful, you should receive a response that repeats like this:

![3d27](https://github.com/user-attachments/assets/3cd64afe-3ec1-4d72-a1bc-19a065404bb2)

Great! We’ve successfully pinged the application server and received a response!

## 4. Create a Bastion host
A bastion host is a dedicated server used to securely access a private network from a public network. To protect our Application Tier from potential outside access points, we will create an EC2 instance in the Web Tier, outside of the ASG. This will be the only server used as a gateway to our application servers.

In the EC2 console, launch a new instance named ‘multiapp-bastionHost.’ We will use the same provisions as before (Amazon Linux 2, t2.micro). Ensure that the appropriate VPC is selected, along with one of the public subnets.

Create a new security group called, ‘brainiac-bastionHost-sg,’ and only allow SSH through My IP.

![3d28](https://github.com/user-attachments/assets/59808aa9-a496-4b2e-bfb1-4a8b8b978282)

Now we have to edit our inbound rules for the multiapp-appserver-sg to make sure we’re allowing SSH access ONLY from the bastion host server.

![3d29](https://github.com/user-attachments/assets/1800b2c2-900d-45f9-87c5-b9c80d3991c9)

## Test the connection
Let’s see if we can connect to our application server through our bastion host.

IMPORTANT: To SSH into our app server, we need to ‘forward’ our key pair from our web server through an SSH Agent. You can watch [this video](https://www.youtube.com/watch?v=cHg6LWOzH98) for a better explanation and demo on how to do this.

In Windows, you'll need to follow these steps:
1. Download and Install PuTTY and Pageant
2. Right-click the Pageant icon in the system tray and select "Add Key." Browse to and select your private key file (usually a .ppk file).

![3d30](https://github.com/user-attachments/assets/716ea579-4657-4d3e-9d3c-ec1aa7ea3b4e)

3. Open PuTTY and load the session configuration for your web server. In the PuTTY Configuration window, go to Connection > SSH > Auth.
4. Check the box labeled “Allow agent forwarding.”
5. Go back to Session, and save the settings if you want to reuse them later.
6. Use PuTTY to connect to your web server. Once connected, Pageant will handle the authentication using your forwarded key.
7. While you are logged into the web server via PuTTY, you can now SSH into the app server using the same SSH key.

![3d31](https://github.com/user-attachments/assets/4cbb7b6f-fc8a-4ed2-b798-648b26c21480)

We’ve successfully built the Application Tier architecture for our Brainiac application! This is the ‘Backend’ layer, where our source code resides and backend operations send and retrieve data to and from the Web Tier and Database Tier.










































