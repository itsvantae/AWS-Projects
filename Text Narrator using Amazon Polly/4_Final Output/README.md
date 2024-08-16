# Checking the ouput
We have completed with the code configuration of the Lambda function, let’s test the function out by creating a test event.
1. Click on Test and configure a test event for your Lambda function.
2. Provide a name for your test configuration and in the Event JSON, provide the text you want to be converted to audio in the form:
   ```
   {
	"text":"The text to be converted to Audio"
   }
   ```
3. Leave the rest of configurations as default and click ‘Save’.
4. Click on Test button again to invoke the test event.
5. Check the output.

   ![3 e](https://github.com/user-attachments/assets/21df2662-7928-48d5-9b3f-c84661eac7e6)

6. You can access the audio file by checking it in the previously created S3 bucket and downloading it.

   ![3 gg](https://github.com/user-attachments/assets/b552e27e-da03-43f1-974f-1096984025a2)


   






   
