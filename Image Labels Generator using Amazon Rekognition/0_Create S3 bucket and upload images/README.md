# Create an Amazon S3 Bucket
1. Log in to your AWS Management Console.
2. Navigate to the Amazon S3 service using the search bar. An S3 bucket functions as a virtual storage container in the cloud, where you can securely store and 
   manage your files. It allows for easy access and control over permissions.

   ![2-1](https://github.com/user-attachments/assets/d2fefe88-597f-4b86-8dc5-e52d4cb6e6a7)

3. Click on ‘Create Bucket’.
4. Choose a unique name for your bucket and select the region the want the storage bucket.

   ![2-2](https://github.com/user-attachments/assets/82f5fab9-f2fb-427d-9c7e-5519b153ee61)

5. Leave the default settings for the rest of the options and click ‘Create Bucket’.
6. We will use this bucket to store the images on which labels are to be generated. Let's proceed by uploading some images to the S3 bucket.

# Upload Images to S3 Bucket
1. Once the bucket is created, navigate to the bucket.
2. Click on the ‘Upload’ button and choose the images you want to analyze from your system.

   ![2-3](https://github.com/user-attachments/assets/99404607-4a06-42da-8b10-d2893c6566bc)

3. Click on Upload. Your image has now been uploaded in the S3 bucket.

   ![S3](https://github.com/user-attachments/assets/d6c3f982-3b5d-4513-9684-25cb669a028a)

4. We’ll use these images for labeling, so try to upload images with multiple objects to test the model’s accuracy in identifying various labels. For example, you 
   could use a photo of a busy city street.

Let’s move forward to the next section, [Install and configure AWS CLI](../Install%20and%20configure%20AWS%20CLI/README.md)



   






   

   








   
   

   








