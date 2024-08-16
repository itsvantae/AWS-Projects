# Creating a Lambda function
1. From your AWS management console, navigate to Lambda from the search bar.
2. Click on Create function.
3. Assign an appropriate name to the Lambda function and select Node.js 16.x as the runtime environment.
4. Toggle the option ‘Change default configuration role’ and check ‘Use existing role’.
5. Choose the role that you created earlier, leave the rest of configurations as default and click Next.

   ![3 c](https://github.com/user-attachments/assets/0ba0d646-a353-4d8b-8adc-bee1f0477228)

   ![3 d](https://github.com/user-attachments/assets/81fbf342-c18f-439c-82a2-04ddf90c540f)

6. Rename your ‘index.mjs’ file to ‘index.js’.
7. We’re using Amazon’s AWS SDK to interact with two services: Polly (for converting text to speech) and S3 (for storing files).

   ```sh
   const AWS = require('aws-sdk');
   const polly = new AWS.Polly();
   const s3 = new AWS.S3();
   ```
8. We’re writing a function that AWS will execute whenever a specific event occurs. It’s like a small program that waits for a trigger to start running.

   ```
   exports.handler = async (event) => {
   ```
9. When the function receives a message with text, it will convert the text into speech. We decide how the speech will sound and what format it should be in

   ```
   const text = event.text;

   const params = {
   Text: text,
   OutputFormat: 'mp3',
   VoiceId: 'Joanna' // You can change this to the desired voice
   };
   ```
10. We send the text to Polly and ask it to turn it into speech. Polly does its magic and gives us back the speech as data.
11. We then save this speech in our S3 storage.

    ```
    const data = await polly.synthesizeSpeech(params).promise();

    const key = `audio-${Date.now()}.mp3`;

    const s3Params = {
    Bucket: 'your-bucket-name', // Replace with your S3 bucket name
    Key: key,
    Body: data.AudioStream,
    ContentType: 'audio/mpeg'
    };

    await s3.upload(s3Params).promise();
    ```
12. We generate a message indicating that the speech has been successfully saved with its unique name in our storage. If an error occurs, an error message will be 
    generated.

    ```
    const outputMessage = `The audio file has been successfully stored in the S3 bucket by the name ${key}`;

    return {
    statusCode: 200,
    body: JSON.stringify({ message: outputMessage })
    };

    } catch (error) {
    console.error('Error:', error);
    return {
        statusCode: 500,
        body: JSON.stringify({ message: 'Internal server error' })
        };
    }
    ```
# Final Code
Your complete Lambda function code will look like this.

```
const AWS = require('aws-sdk');

const polly = new AWS.Polly();
const s3 = new AWS.S3();

exports.handler = async (event) => {
    try {
        // Extract text input from the event
        const text = event.text;
        
        // Specify parameters for Polly
        const params = {
            Text: text,
            OutputFormat: 'mp3',
            VoiceId: 'Joanna' // You can change this to the desired voice
        };

        // Synthesize speech using Polly
        const data = await polly.synthesizeSpeech(params).promise();

        // Generate a unique key for the audio file
        const key = `audio-${Date.now()}.mp3`;

        // Specify parameters for S3
        const s3Params = {
            Bucket: 'your-bucket-name', // Replace with your S3 bucket name
            Key: key,
            Body: data.AudioStream,
            ContentType: 'audio/mpeg'
        };

        // Upload audio file to S3
        await s3.upload(s3Params).promise();

        const outputMessage = `The audio file has been successfully stored in the S3 bucket by the name ${key}`;

        return {
            statusCode: 200,
            body: JSON.stringify({ message: outputMessage })
        };
    } catch (error) {
        console.error('Error:', error);
        return {
            statusCode: 500,
            body: JSON.stringify({ message: 'Internal server error' })
        };
    }
};
```
14. Deploy the code changes by clicking on Deploy.
    




   
   
