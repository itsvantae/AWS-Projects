# Creating a bucket in Amazon S3
1. In the AWS Management Console, on the Services menu, choose S3.
2. Choose Create bucket
   
   An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS accounts in any AWS Regions can use the 
   name of that bucket unless you delete the bucket.

   For this project, you use a bucket name that includes a random number, such as website-123.

3. For Bucket name, enter `website-<123>` and replace <123> with a random number.

   Public access to buckets is blocked by default. Because the files in your static website will need to be accessible through the internet, you must permit public 
   access.

4. For Object Ownership, choose ACLs enabled.
5. Choose Bucket owner preferred.
6. For Block Public Access settings for this bucket, clear the check box for Block all public access, and then select the box that states I acknowledge that the 
   current settings might result in this bucket and the objects within becoming public.
7. For Bucket Versioning, choose Enable.
   
   Note: Once you turn on (enable) bucket versioning, you can't turn it off.

8. For Tags, choose Add tag, and enter the following:

   * Key: `Department`
   * Value: `Marketing`

9. Choose Create bucket

![screencapture-us-east-1-console-aws-amazon-s3-bucket-create-2024-08-18-15_04_35](https://github.com/user-attachments/assets/ffab1d3e-2a28-4502-9f76-453ca631bf43)


Your S3 bucket is ready, now we'll be configuring our static website on the bucket
      
   
