# Turning on Public Access to the objects
Objects that are stored in Amazon S3 are private by default. This setting helps keep your organization's data secure.

In this session, you make the uploaded objects publicly accessible so users can view your website.

First, confirm that the objects are currently private.

Return to the browser tab that showed the 403 Forbidden message.

Refresh  the webpage.

![Screenshot 2024-08-18 154504](https://github.com/user-attachments/assets/caae567a-2301-413c-aba4-4a858aa98528)

You should still see a 403 Forbidden message. This response is expected! This message indicates that your static website is being hosted by Amazon S3 but that the content is private.

You can make Amazon S3 objects public in two ways:

* To make an entire bucket or a specific directory within a bucket public, use a bucket policy.
* To make individual objects within a bucket public, use an access control list (ACL).

It's generally safer to make individual objects public, as this helps prevent accidentally exposing other objects. However, if you're certain that the entire bucket contains no sensitive information, you can opt for a bucket policy.

In this step, you'll configure individual objects to be publicly accessible.

1. Keep the website tab open, and return to the web browser tab with the Amazon S3 console.
2. Choose  all three objects.
3. In the Actions menu, choose Make public using ACL.

   ![Screenshot 2024-08-18 154818](https://github.com/user-attachments/assets/d3eb872f-5d6a-48e8-aae6-145cb8655908)

   A list of the three objects is displayed. Choose Make public
   
   Your static website is now publicly accessible.

4. Choose Close
5. Return to the web browser tab that has the 403 Forbidden message.
6. Refresh  the webpage.

   ![Screenshot 2024-08-18 154947](https://github.com/user-attachments/assets/02b4697b-1550-4bef-90fc-8b5fd6517b16)

   You should now see the static website that is being hosted by Amazon S3.
