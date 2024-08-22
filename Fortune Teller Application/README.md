# Overview of Project
Build a serverless application using AWS Lambda that provides random responses ("Yes," "No," or "Maybe") to user questions. This guide will walk you through setting up a Lambda function, deploying it, and integrating it with API Gateway.

# Step #1: Set Up an AWS Lambda Function
* Open the AWS Management Console and navigate to the Lambda service.
* Click "Create function" and select "Author from scratch".
* Enter a name for your function and select a runtime (e.g., Python 3.8).
* Under "Function code", write or upload the code for generating random responses.
* Configure the function settings, such as memory, timeout, and execution role.
* Go to configuration and choose edit in General configuration to configure the settings and save the changes.

  ![fortune teller 1](https://github.com/user-attachments/assets/d88cb9b2-cc03-4d79-97c6-f68a93a18ed4)

# Step #2: Write the Fortune-Telling Code
* Import the random module in Python.
* Define a function that generates a random integer between 1 and 3.
* Use conditional statements to map the random integer to a response (e.g., 1 = "yes", 2 = "no", 3 = "maybe").
* Return the response as the output of the Lambda function.

```
import random

def lambda_handler(event, context):
    # Generate a random integer between 1 and 3
    random_number = random.randint(1, 3)
    
    # Map the random number to a response
    if random_number == 1:
        response = "Yes"
    elif random_number == 2:
        response = "No"
    else:
        response = "Maybe"
    
    # Return the response as the output
    return {
        'statusCode': 200,
        'body': response
    }
```

* Copy the code into the **"Function code"** section of your Lambda function and click **"Deploy"** to save and apply the changes.

  ![fortune teller 1](https://github.com/user-attachments/assets/5f81d4e9-2583-4b31-8e2b-fb5e60796cbc)

# Step #3: Set Up an API Gateway
* Open the API Gateway service in the AWS console.
* Click "Create API" and choose "HTTP API".
* In Step 1, create an API by clicking **"Add integration"**, select **"Lambda function"**, and choose the Lambda function you created. Name your API and click **"Next"**.

  ![1](https://github.com/user-attachments/assets/1b87cbd7-7699-46ca-8519-6dc741f39608)

* Define the route, method (e.g., GET), and integration type (Lambda function). Click next.
  
  ![fortune teller 2](https://github.com/user-attachments/assets/25f4c98d-2d1b-48ac-bfeb-748d092be6d8)

*   
  




  





