# Securely sharing an object using a presigned URL
When you need to temporarily and securely share an object with someone, you can create a presigned URL. While creating the URL, you'll set the duration for which it remains valid. After that, you can share the URL with the users who need access to the object.

As long as the presigned URL is valid, anyone with it can access the object. Be sure to limit the URL's validity period to what's necessary and only share it with trusted individuals.

1. Choose `new-report.png` and download the file to your computer.
   
   Ensure that the file keeps the same file name, including the extension.

2. Return to the Amazon S3 console, and choose the Objects tab.
3. Choose Upload
4. Choose Add files
5. Choose the file that you downloaded.
6. Choose Upload. You have uploaded your file to the bucket.
7. Choose Close

   Like when you first uploaded the website files, the new-report.png file is private by default. This time, instead of making the object public, you create a 
   presigned URL to access the file.

8. In the Objects tab, choose  new-report.png.
9. From the Actions menu, select Share with a presigned URL

    ![Screenshot 2024-08-18 155830](https://github.com/user-attachments/assets/7e8c259a-43ff-452c-8587-304581cee603)

10. In the pop-up window, configure the Time interval until the presigned URL expires:
    
    * Choose Minutes
    * For Number of minutes, enter 2
   
      ![Screenshot 2024-08-18 160016](https://github.com/user-attachments/assets/31993ef7-af5d-49d5-b6ed-ca2eb490d4ad)

11. Choose Create presigned URL
12. From the banner at the top of the page, choose Copy presigned URL.
13. Open a new browser tab, and paste the URL you copied into the address bar.

The report will be displayed in the web browser.

If you wait 5 minutes and try using the link again, you’ll see that the URL has expired and no longer functions.


