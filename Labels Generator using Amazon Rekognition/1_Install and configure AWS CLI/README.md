# Installing the AWS Command line interface(CLI)
The AWS CLI is used to interact with various AWS services from the command line. To install AWS CLI:

1. Open your terminal or command prompt.
2. Run the command appropriate for your operating system to install the AWS CLI.

   ```sh
   #For Windows:
   msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

   #For macOS (using Homebrew):
   brew install awscli

   #For Linux (using package manager):
   sudo apt-get install awscli
   ```
   
   To check if the AWS CLI (Command Line Interface) was installed successfully on your system, you can run the following command in your terminal or command prompt:
    ```sh
    aws --version
    ```
    Note: Restart your terminal if it is giving not installed error
   
    You have successfully installed the CLI. Next, we need to configure the CLI with the appropriate user keys to get started with using AWS services.

# Configure AWS CLI
1. To configure your AWS CLI, run the following command in your terminal:
   ```sh
   aws configure
   ```
2. Running this command will ask for a access key and secret access key.
   What are these? To access your AWS account from CLI, you need to set up a user account associated with it and these keys are used for the authentication for 
   accessing the AWS services.
3. Login to your AWS Management console and search for IAM in the search bar.
4. Navigate to Users and click on Create User.
5. Give an appropriate user name and click Next.

   ![2-3](https://github.com/user-attachments/assets/ac13d3c7-d808-4f25-bfdd-a79bedd8e8d8)

6. For the Permission options, choose the option ‘Attach policies directly’ and attach the ‘AdministratorAccess’ policy.

   (Be careful while using the Administrator Access policy as we get the full access to the AWS services and is generally not recommended if the user will be 
   accessed by someone else).

   ![2-4](https://github.com/user-attachments/assets/066db092-1b27-42d9-9beb-0bc5d7691b95)

7. Click on Next and Create User.
8. Navigate to the user you created, and click on create Access key under the Access Keys option.

   ![IAM](https://github.com/user-attachments/assets/0b3749d1-2e9a-47cc-8278-d58d77ffd0fd)

9. Choose the Command Line Interface(CLI) as the use case, check the confirmation box and click Next.
10. Provide a suitable description about purpose of the Access key and Create Access Key.
11. You will receive an Access Key and a Secret Access Key. These keys grant access to your AWS services, so be sure to keep them confidential and secure.
12. Some best practices while using Access Keys:
    - Never store your access key in plain text, in a code repository, or in code.
    - Disable or delete access key when no longer needed.
    - Enable least-privilege permissions.
    - Rotate access keys regularly.
13. Go back to your terminal or command prompt and paste the keys that you just generated.
14. Choose the region (Make sure the CLI default region and the S3 bucket region are the same)
15. The general flow of the command line would look like:
    ```sh
    PS H:\AWS-beginner-friendly-projects\Image label> aws configure
    AWS Access Key ID [****************L4TV]: ****************
    AWS Secret Access Key [****************mtjR]: *******************
    Default region name [us-east-1]: us-east-1
    Default output format [None]: None
    ```
   We’ve configured our AWS CLI. Next, we’ll move to [2_Import Libraries](https://github.com/itsvantae/AWS-Projects/tree/main/Image%20Labels%20Generator%20using%20Amazon%20Rekognition/2_Import%20Libraries) where we will import the necessary libraries required for 
   execution.







 


   

   
   
   








