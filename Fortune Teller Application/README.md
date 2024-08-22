# Overview of Project
Build a serverless application using AWS Lambda that provides random responses ("Yes," "No," or "Maybe") to user questions. This guide will walk you through setting up a Lambda function, deploying it, and integrating it with API Gateway.

# Step #1: Set Up an AWS Lambda Function
* Open the AWS Management Console and navigate to the Lambda service.
* Click "Create function" and select "Author from scratch".
* Enter a name for your function and select a runtime (e.g., Python 3.8).
* Under "Function code", write or upload the code for generating random responses.
* Configure the function settings, such as memory, timeout, and execution role.
* Go to configuration and choose edit in General configuration to configure the settings and save the changes.

  ![fortune teller](https://github.com/user-attachments/assets/9fe828c5-bfc2-4625-bb2f-10c86e616c47)

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

  ![ftt](https://github.com/user-attachments/assets/fb443dfe-f81f-4b6b-823f-052d6f2196f8)

# Step #3: Set Up an API Gateway
* Open the API Gateway service in the AWS console.
* Click "Create API" and choose "HTTP API".
* In Step 1, create an API by clicking **"Add integration"**, select **"Lambda function"**, and choose the Lambda function you created. Name your API and click **"Next"**.

  ![fortune teller 1](https://github.com/user-attachments/assets/db8ec5a0-50f8-4e2b-96aa-afc0deeebc53)

* Define the route, method (e.g., GET), and integration type (Lambda function). Click next.
  
  ![fortune teller 2](https://github.com/user-attachments/assets/25f4c98d-2d1b-48ac-bfeb-748d092be6d8)

*   In step 3, Create stage name (e.g., "prod") and click next.
*   Review and create your API Gateway.

# Step #4: Deploy Your Code
* In the API Gateway console, click "Deployments" and then "Create."
* Select the stage (e.g., "prod") and deploy the API.
* Copy the API endpoint URL, which users will use to access the fortune teller.
* To test your API Gateway, paste your endpoint URL into your web browser and press **Enter**.

  ```
  <API-URL>/<Stage-name>/<lambda-function-name>
  ```
* You will see a response of "Yes," "No," or "Maybe" each time you refresh the page.

  ![exam](https://github.com/user-attachments/assets/7091c0e1-3ab6-460f-a8ef-15f261568ca0)

# Step #5: Test Your Code
* Create a free account on Postman and use it to send an API request.

  ![ft](https://github.com/user-attachments/assets/1ab648fb-409f-44e3-95a7-2c4676c64a78)

* Paste your URL into the request field and click **"Send"**.

  ![ft1](https://github.com/user-attachments/assets/71dc5993-5f2b-4007-b97e-72c929bf5650)

* Verify that you receive a "yes", "no", or "maybe" response to each question.
* Try asking different questions to see if the magic of randomness works and watch the fortunes change!

  ![exam1](https://github.com/user-attachments/assets/295e7a4c-4607-4719-84ab-948aef01dd08)

  ![exam2](https://github.com/user-attachments/assets/29ae3c50-c7fa-47f6-a371-52f41acc5e35)

  ![exam3](https://github.com/user-attachments/assets/fc73f84a-3281-45a2-8a57-d71dafa0b969)

Congratulations! You've successfully created your Fortune Teller application using AWS Lambda. Now, whenever you ask a question, you'll receive a whimsical response of "Yes," "No," or "Maybe." Enjoy the randomness and let the fortunes guide you!
  





  
 

  




  





