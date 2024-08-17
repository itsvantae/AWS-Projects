# Specify Intent and Slots

![Screenshot 2024-08-17 113402](https://github.com/user-attachments/assets/988432cb-174e-4670-878b-7cc6abd6f55d)

Let's first go over some key terms used in Amazon Lex:

- **Intent**: The objective or purpose behind the user's input.
- **Utterance**: The specific words or phrases the user says or types.
- **Slots**: Specific details or variables within the user's input that the system needs to identify.
- **Fulfillment**: The action or response the system performs based on the user's intent and the information gathered from the slots.

Take a look at this example:

In a flight booking chatbot, the intent represents what the user wants to do, like booking a flight or checking flight status. Utterances are the user's input, such as "I need a ticket to New York." Slots are the key details in these utterances, like destination, date, and seat class. Fulfillment is the chatbot's action, booking the flight and providing confirmation.

Now that we are familiar with the basic terms, let’s start with building our chatbot.
1. In the Intent details, fill in an appropriate Intent name and description.

   ![4d](https://github.com/user-attachments/assets/ed401e37-04ab-41fa-a49e-6488b74c25f4)

2. In the sample utterances, add some inputs that can be asked by the user. Amazon Lex will try to understand the user input by aligning the input with the 
   utterances provided.

   ![4e](https://github.com/user-attachments/assets/69d5cee1-2284-41e0-afe9-7f8449e870c7)

3. Go to the slots section and click on "Add Slot." We need to capture the language in which the text should be translated as a slot. To do this, first, create the 
   Slot type. After setting it up, go back and click on "Save Intent".
4. Click on back to Intents list and navigate to slot type, add Slot type.
5. Choose ‘Add blank slot type’ and give a name to the slot type (here ‘language’).

   ![4f](https://github.com/user-attachments/assets/ff7a5f3d-17cd-40ce-9824-5fb4a4e7ca4e)

6. Add some languages as Slot type values similar to given below:

   ![4g](https://github.com/user-attachments/assets/561b258e-f498-4e49-9d16-9f72a865fbb8)

   (Let us go with the same slot type values for now instead of adding new ones as there would be modifications required in the Lambda function too)

7. Click on Save slot type.
8. Navigate back to the Intents to use this slot type for our slot.

   ![4h](https://github.com/user-attachments/assets/a9ba5ddb-bf39-4e80-a8b2-fa8738cddb11)

9. Click on Add Slot. Give the slot name and choose the slot type ‘language’ previously made. Write the prompt where the chatbot asks for user choice for language 
   translation.
10. Click on Add.
11. Create another slot named ‘text’ to capture the input text that needs to be translated. Select `AMAZON.FreeFormInput` as the slot type, and enter an 
    appropriate prompt asking for the text to be translated. Then, click on "Add".

    ![4i](https://github.com/user-attachments/assets/5ed7c812-c306-411a-babb-31b3241f6b18)

12. We can add some more utterances specifying the Slots.

    For example : Instead of ‘I want to translate’ , if user inputs ‘I want to translate to French’ with the language specified in the starting intent itself, it 
    should not ask for the language again by running the language prompt. Instead we can specify Slots like below:

    ![4j](https://github.com/user-attachments/assets/06b0092c-8c7c-44ef-987b-20c40deb4505)

    This will automatically understand the language slot type if already specified and ask for the input text to be translated directly.

13. We can also add an Initial response to the initial intent as a feedback message.

    ![4k](https://github.com/user-attachments/assets/14390ae5-22c6-431b-88ac-62353935af45)

    


    

 

   

   

   


   

   



