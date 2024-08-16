# Creating an IAM role
1. In this project, we will access the Amazon Polly service and store the audio output in an S3 bucket using a Lambda function.
2. To achieve this, we need an IAM role with the appropriate policies attached.
3. From your AWS management console, search for IAM from the search bar.

   ![Screenshot 2024-08-16 185919](https://github.com/user-attachments/assets/55c22265-a986-4c62-903c-316ed9e4be1c)

4. Navigate to Access Management → Roles → Create Role.
5. Select AWS service as the trusted entity type and Lambda as your use case. Click on Next.

   ![01](https://github.com/user-attachments/assets/09859b9f-6203-4514-9f0c-178545f2da04)

6. From the list of permission policies, choose the following policies :
   a. AmazonPollyFullAccess
   b. AmazonS3FullAccess
   c. AWSLambdaBasicExecutionRole
7. Click on Next.
8. Provide a suitable name and description for the IAM role and click on Create role.

   ![Screenshot 2024-08-16 190840](https://github.com/user-attachments/assets/85ec96d9-7f3e-4018-9b0c-bb66ec9708e8)



   
 

