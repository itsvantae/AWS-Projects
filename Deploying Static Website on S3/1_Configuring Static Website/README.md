# Configuring a static website on Amazon S3
1. In the Buckets section, choose the name of your new bucket.
2. Choose the  Properties tab.
3. Scroll to the Static website hosting panel.

   ![Screenshot 2024-08-18 151807](https://github.com/user-attachments/assets/b19f0b1a-bca6-40ed-bdf3-d98043ee6b87)

4. Choose Edit
5. Configure the following settings:

   * Static web hosting: Choose Enable.
   * Hosting type: Choose Host a static website.
   * Index document: Enter `index.html`
   * Error document: Enter `error.html`
   
   Note: You must enter index.html and error.html even though they are already displayed.

6. Choose Save changes
7. In the Static website hosting panel under Bucket website endpoint, select the link and paste it into your web browser.

   ![Screenshot 2024-08-18 152053](https://github.com/user-attachments/assets/25598b86-f65f-4996-98bb-8ba740f4ae79)

You receive a 403 Forbidden message because you have not yet configured the bucket permissions. Keep this tab open in your web browser so that you can return to it later.

You have configured your bucket to host a static website.   
