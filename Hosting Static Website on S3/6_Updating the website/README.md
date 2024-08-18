# Updating the website
Although you've set a policy to prevent the deletion of website files, you can still update the site by editing the HTML file and re-uploading it to the S3 bucket. In Amazon S3, you must upload the entire file to replace the existing one, as you can't edit an object directly.

1. On your computer, open the index.html file using a text editor like Notepad or TextEdit.
2. Locate the text that says `Served from Amazon S3` in the file. Replace it with "Created by <YOUR-NAME>," substituting <YOUR-NAME> with your actual name (e.g., 
    "Created by Jane").
3. After making the changes, save the updated `index.html` file.
4. Go back to the Amazon S3 console and upload the newly edited `index.html` file to your S3 bucket.
5. Choose `index.html`, and in the Actions menu, choose the Make public using ACL option again.
6. Choose Make public.
   
Return to the web browser tab with the static website, and refresh the page.  

Your name should now appear on the page.

Your static website is now live on the internet. Hosted on Amazon S3, it offers high availability and can handle large volumes of traffic without relying on any servers.
