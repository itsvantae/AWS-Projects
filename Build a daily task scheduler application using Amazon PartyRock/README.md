# Build a daily task scheduler application using Amazon PartyRock

# Project Overview: ☁️
In this project, we'll be using PartyRock to develop a 'Daily Task Scheduler Application' that enhances productivity and organization. PartyRock, powered by Amazon Bedrock, is a fun and intuitive generative AI app-building playground. It enables you to create a variety of apps without needing any coding experience, making it accessible to everyone, not just developers.

PartyRock is designed to empower builders of all levels by providing a simple and engaging way to start creating with generative AI. With just a few easy steps, you can experiment with different AI models, learn how to craft effective AI prompts, and share the applications you create.

Building and experimenting with PartyRock not only gives you hands-on experience with AI but also helps you understand how to leverage its capabilities effectively. I've been exploring PartyRock recently and found it incredibly fun to use, and I'm excited for you to experience it too while building this project.

# Steps to be performed: 
We'll be going through the following steps to create our project:

1. Generating the daily task scheduler application
2. Changes in existing widgets
3. Adding new widgets
4. Publishing your app

# Services Used 🛠
AWS PartyRock: A user-friendly platform from AWS that lets you create AI-powered apps easily, without any coding skills. It’s designed to help you build and experiment with applications using generative AI in a straightforward and enjoyable way.

# How to Get Started
1. Visit the website : https://partyrock.aws/

 ![partyrock_webpage](https://github.com/user-attachments/assets/61049634-33b4-4841-b761-62278bb0f26b)

 2. Create your first application by clicking on ‘Build your own app’.
 3. Describe what you would like the app to do. Let’s go for something fun here!

    ![partyrock11](https://github.com/user-attachments/assets/458e0d6b-1604-4e23-969c-13335da1030c)

4. Click on Generate app and let PartyRock do the work for you!

   ![1110](https://github.com/user-attachments/assets/712cbe1d-948e-4c04-a2fe-19cc36c154e6)

5. We just created an application without any coding pre-requisites, using prompt engineering in less than 5 minutes !
6. We can also customize applications created by others by clicking the 'Remix' button at the top right of the application page, allowing us to make a copy and 
   modify it according to our preferences.

In the next step, we'll begin building our Application by modifying the existing components and introducing some new ones.

# Generating the daily task scheduler application
1. Navigate to AWS PartyRock : https://partyrock.aws/
2. Click on ‘Build your own app’ and enter an appropriate prompt.

   ![prompt](https://github.com/user-attachments/assets/d68d5763-c4b2-4b0e-a303-36c4174b886f)

3. Click on ‘Generate App’ and wait for PartyRock to do the work for you!

   ![taskschedule_app](https://github.com/user-attachments/assets/4127f3f9-ad48-42f4-81e8-52a65811fd5d)

4. PartyRock created an application that accepts tasks as input, prioritizes them to generate a schedule, and even includes a chatbot to help refine your plan!

In the next section, let's try modifying the existing components to make them more specific.

# Modify existing widgets
1. You can resize the blocks present by clicking and dragging the bottom right corner of the block for organizing them.
2. You can edit your widget by clicking on the Edit option in the top right corner.

   ![editwidget](https://github.com/user-attachments/assets/0be98ab0-aabc-41e0-8fba-e5397fcd7a5f)

3. In the Edit section of the Schedule widget, you have several models available. You can select one of these models to generate your outputs, depending on the 
   desired level of output quality. Let's take a look at a comparison:

   ## Claude 3 Sonnet
   
   ![claude 3 sonnet](https://github.com/user-attachments/assets/be0fa8c5-651c-487a-b241-457042ee85e0)

   ## Jurassic-2 Ultra

   ![Jurassic 2 ultra](https://github.com/user-attachments/assets/47ec4022-2b58-4f97-bf8b-916e9de822ae)

Both models provided outputs based on different aspects: one detailing the entire day’s timeline, including specific activities and times, while the other focused on the time required for each activity.

4. The ‘prompt’ section from Edit Schedule tab is used to provide prompt to the model on which the output is generated. We can reference a widget using 
   @widget_name in the prompt.
   
In the next lesson, let's try adding some more widgets and further customize the application.

# Adding new widgets
1. Let’s try to add a time widget that takes the approximate time required for each task.
2. Click on ‘Add Widget’ on the top left of your screen to add a widget. Choose an user input widget.
3. You can change the name and placeholder of your widget.

   ![TimeWidget](https://github.com/user-attachments/assets/51bc0407-52d0-44a5-b5db-70479a28d41a)

4. Now let’s give this widget as an input for preparation of schedule. We can change the prompt to enter the time required for each task.

   ![editedSchedule](https://github.com/user-attachments/assets/9a69c3a8-3a0d-4030-a7ef-82185e2d5846)

5. Click on Save and check your new schedule.

   ![updatedApp](https://github.com/user-attachments/assets/b580bad5-a168-4c15-beef-ba0b9cb479f4)

6. Let’s also add a widget for song recommendations to uplift your mood and an image generator that complements the song to help kickstart your day.

   ![newWidget](https://github.com/user-attachments/assets/26d7bd01-9d5c-425b-b3a3-d35220ecc0bf)

   You can also choose the your image style preference from the provided Style presets.

7. Feel free to get creative and customize the widgets however you like. Try adding unique features or making adjustments to enhance your experience and have fun 
   with the process! Here's the final output

   ![final_output](https://github.com/user-attachments/assets/9ebcad69-8aa8-461c-9a6d-b736e1d178a5)
   
   In the next section, we will be publishing our application and sharing it with the world.

# Publishing your application
1. Great job creating your application! With PartyRock, you can take it even further by publishing your app for others to enjoy and use!
2. Click on ‘Make public and share button’ present on the top right corner of the website.

   ![public](https://github.com/user-attachments/assets/bc680027-06a6-451e-968d-e0d36e93e22b)

3. Anyone with this link can see, use or remix your application.

Here is my Daily Task Scheduler application : https://partyrock.aws/u/vantaee/vpWvjhS_c/NightSched












   








   


   












   


   

















   










   














