# Testing the Lambda function
1. To test the Lambda function, click on Test and configure the Test event.
2. Give a suitable name to the test event and keep the Event JSON in the format below:

```
   {
   "sessionState": {
     "intent": {
       "name": "TranslationIntent",
       "slots": {
         "text": {
           "value": {
             "interpretedValue": "Hello",
             "originalValue": "Hello"
           }
         },
         "language": {
           "value": {
             "interpretedValue": "French",
             "originalValue": "French"
           }
         }
       }
     }
   }
 }
```

# Testing the Lambda function
The reason that we are providing this format is because your Lambda function gets an input from the Amazon Lex in this specified format.

Save the test event and click on Test again to Invoke the event.

![4r](https://github.com/user-attachments/assets/a1376fc1-070b-4586-bbce-8768520c04c1)

The function gives an output in a JSON format which is the required format to give an input for Amazon Lex. It will get the message content and display it to the user.

Next, let’s test out the chatbot working.






