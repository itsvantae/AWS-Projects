# Configuring a static website on Amazon S3 

# Overview of Project ☁️
This project focuses on hosting a static website using Amazon S3. Static websites include HTML pages, images, style sheets, and other files necessary for rendering a website. Unlike dynamic websites, static websites do not rely on server-side scripting or databases, though they may use client-side scripts that execute in the user’s web browser.

With Amazon S3, you can easily host a static website by uploading your site’s content and configuring it to be accessible to users. This approach eliminates the need for server management, leveraging S3 to store and serve data reliably from anywhere on the web, at any time.

# Steps to be performed
We'll be going through the following steps to complete our project:

1. Create a bucket in Amazon S3.
2. Configure a bucket to host a static website.
3. Upload content to a bucket.
4. Turn on public access to bucket objects.
5. Securely share a bucket object using a presigned URL.
6. Secure a bucket using a bucket policy.
7. Update the website.
8. View object versions in the Amazon S3 console.

# Services Used 🛠 
* Amazon S3: Stores and delivers your website files. Once uploaded and configured for static website hosting, S3 handles all storage, retrieval, and delivery of 
  your content directly to users over the internet.

# Architectural Diagram
This is the architectural diagram for the project

![Screenshot 2024-08-18 145420](https://github.com/user-attachments/assets/e746719c-e47c-4828-b6e3-01a8ca547195)

# Clean-up
Login to the **AWS Management Console** and go to **S3** using the search bar. Select the **S3 bucket** used for hosting the website. Click on **Empty** in the top-right corner to remove all objects within the bucket.

After emptying the bucket, choose the **Delete** option in the top-right corner of the S3 bucket page to delete the bucket.














 



