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
"arn:aws:s3:::website-1234/index.html",
"arn:aws:s3:::website-1234/script.js",
"arn:aws:s3:::website-1234/style.css"
```



