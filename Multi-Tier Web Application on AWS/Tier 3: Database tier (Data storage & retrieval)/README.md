# Database tier
Almost there! Now it’s time to build the final tier of our Brainiac application architecture: the Database. Every application needs a way to store important data, such as user login information, session data, transactions, and application content. Our application servers need to read and write to databases to perform necessary tasks and deliver the right content and services to the Web Tier and users.

We will use a Relational Database Service (RDS) with MySQL.

Here’s what we’ll build:

- A database security group that allows both inbound and outbound MySQL requests to and from our application servers.
- A DB subnet group to ensure the database is created in the appropriate subnets.
- An RDS database running MySQL.

## 1. Create a database security group
Our application servers need a way to access the database, so let’s first create a security group that allows inbound traffic from the application servers.

Create a new security group called, ‘multiapp-db-sg.’ Make sure your vpc is selected.

Now, we need to add inbound AND outbound rules that allow MySQL requests to and from the application servers on port 3306.

![3d32](https://github.com/user-attachments/assets/cb823ed1-83a5-4022-84b7-f494296bb5d5)

![3d33](https://github.com/user-attachments/assets/dd8f1f6f-9e80-467e-8950-22fe53cd5ef8)

We’ll need to do the same for the 'multiapp-appserver-sg'.

![3d34](https://github.com/user-attachments/assets/c5a5b483-a4b3-45f5-8606-001fbba880ff)

![3d35](https://github.com/user-attachments/assets/5863a46f-489d-44e9-8baa-b0b0942e617f)

## 2. Create a DB subnet group
In the RDS console, under the ‘Subnet groups’ sidebar menu, create a new subnet group called, ‘multiapp-db-subnetGroup.’ Make sure your VPC is selected.

Remember from our diagram, we want the database located in -subnet-private3 and span multiple AZs and subnets, if necessary.

Select our two AZs (us-east-1 and us-east-2) and our private subnets (-subnet-private3 and -subnet-private4). Unfortunately, the selection dropdown, doesn't provide the subnet names, so we might have to navigate back to our main Subnets dashboard to get the right ids.

![3d36](https://github.com/user-attachments/assets/e03fb06f-3aa2-4033-8468-44de555e8daf)

## 3. Create an RDS database
Under the RDS console and the ‘Databases’ sidebar menu, create a new database with a MySQL engine.

For our purposes, we’ll stick to the ‘Free tier’ option.

If we were to use this database for production/dev environments, it’s best practice to enable Multi-AZ deployment for higher availability, but this does incur a cost. Multi-AZ deployments allow us to create a ‘Standby’ or ‘Failover’ database that serves as a back-up, should something happen to our main instance or AZ. It also allows us to create a ‘read-replica’ database, which, essentially, is a read-only version of our DB and allows for more efficient queries from the Application Tier.

![3d37](https://github.com/user-attachments/assets/b18c57fc-b0b9-42e4-8780-acbd6d480842)

We’ll name this database ‘multiapp-webApp-db’ and create a master username and password. We’ll use these credentials to log into the database from the command line, so be sure to keep this information handy.

![bleh](https://github.com/user-attachments/assets/95e571a1-c2f8-4feb-a5ce-ce55365f55b4)

For ‘Instance configuration,’ we’ll use a db.t2.micro and leave the defaults for ‘Storage.’

For ‘Connectivity,’ we do not want to connect an EC2 instance but make sure your VPC is selected.

![bleh2](https://github.com/user-attachments/assets/d615a5e1-cd57-427f-8286-46c6c2a2cd6d)

Select the DB subnet group we created earlier. We also do not want to enable ‘Public access.’

![bleh3](https://github.com/user-attachments/assets/3e175124-6c57-4737-a1c8-4ef3b05f4012)

Choose our brainiac-db-sg security group and select us-east-1a as the preferred AZ.

![bleh4](https://github.com/user-attachments/assets/b3c278a3-6229-4216-922e-db6a69fb6ca7)

Under ‘Additional configuration,’ repeat the name of the database you created in the first step (without dashes).

![bleh5](https://github.com/user-attachments/assets/f7c2a66f-333a-45b2-a8da-1848b38c094f)

Leave the defaults for everything else and create the database (this may take a few minutes to fully provision).

# Connect to the Database
After the DB has been created, we’ll need the database endpoint to establish a connection from the app server.

![3d39](https://github.com/user-attachments/assets/5e13872f-5034-415d-9d09-943722274e67)

If you haven't yet, SSH into the app server through our bastion host.

We should already have mySQL installed on the server, so we can run this command:

```
mysql -h YOUR_DB_ENDPOINT -P 3306 -u YOUR_DB_USERNAME -p
```

When prompted, enter the password you chose when creating the DB.

![3d40](https://github.com/user-attachments/assets/bfa02f98-df1a-4c78-8976-7aeccfeb2598)

Great! We successfully connected to our database from our application server!

# Success! 

That was quite a journey! It wasn’t easy, but we took it step by step and made it through. We’ve successfully created a highly available, 3-tier application architecture that’s now ready!





































