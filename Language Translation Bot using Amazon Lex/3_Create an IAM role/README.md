# Create an IAM role
1. From your AWS management console, navigate to IAM from your search bar.
2. Navigate to roles and Create Role. This role will be used for the Lambda function to provide basic Lambda execution permissions and access to Amazon Translate.
3. Select the trusted entity type as AWS service and select Lambda as the use case. Click on Next.

   ![4n](https://github.com/user-attachments/assets/bfb71e0f-7c7f-4847-83f1-6a848ce654ef)

4. Attach the following policies to the role :
   a. TranslateFullAccess
   b. AWSLambdaBasicExecutionRole
5. Click on Next. Enter a suitable name and description for the role and Create Role.

   ![4o](https://github.com/user-attachments/assets/2d9cdfe2-5643-4f40-8065-4d0730187b6c)

   This role will be used for the Lambda function permission.


   


