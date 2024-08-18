# Using a bucket policy to secure your bucket
You want to protect your website files and make sure that no one can delete them. To do this, you apply a bucket policy that denies delete privileges on your website files.

1. Return to the Amazon S3 console, and choose the Permissions tab.
2. Under Bucket policy, choose Edit
3. Copy the following policy text. In the Policy text editor, replace the existing policy text with this text:

```
{
  "Version": "2012-10-17",
  "Id": "MyBucketPolicy",
  "Statement": [
    {
      "Sid": "BucketPutDelete",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:DeleteObject",
      "Resource": [
        "arn:aws:s3:::<bucket-name>/index.html",
        "arn:aws:s3:::<bucket-name>/script.js",
        "arn:aws:s3:::<bucket-name>/style.css"
        ]
    }
  ]
}
```

4. Next, you update the text in the policy editor. In the following lines of code in the policy editor, replace the  placeholders with the name of your bucket.

```
"arn:aws:s3:::<bucket-name>/index.html",
"arn:aws:s3:::<bucket-name>/script.js",
"arn:aws:s3:::<bucket-name>/style.css"
   ```
   Your updated code should look similar to the following:
   
```
"arn:aws:s3:::website-112/index.html",
"arn:aws:s3:::website-112/script.js",
"arn:aws:s3:::website-112/style.css"
```

   Note: Your bucket name will be different. Be sure to use the name of the bucket that you created.

5. Choose Save changes
6. Return to the Object tab
7. Select `index.html`. Choose Delete.
8. In the Delete objects panel, enter delete to confirm that you want to remove this file.
9. Choose Delete objects

   Notice that the index.html file is listed in the Failed to delete pane.

   ![Screenshot 2024-08-18 161124](https://github.com/user-attachments/assets/e954b1aa-9e57-4827-9394-eaec80113382)

   This confirms that your policy is working and preventing the website's files from being deleted.

Choose Close to return to the Objects tab.





