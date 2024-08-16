# What is Amazon Polly?
Amazon Polly is a service provided by AWS that enables developers to generate human-like speech from text.

- **Text-to-Speech Conversion**: Amazon Polly turns written text into spoken words. So, you can type something, and Amazon Polly will say it out loud in a natural-sounding voice.
- **Realistic Speech**: The speech created by Amazon Polly sounds like a real person speaking, not robotic or unnatural. It's great for making computerized voices sound more human-like.
- **Options to Customize**: You can change how the speech sounds. For example, you can make it faster or slower, adjust the pitch (high or low), and even pick different accents or languages.
- **Supports Many Languages and Voices**: Amazon Polly can speak in lots of different languages and with different voices. Whether you want a man or a woman, or someone with a British or American accent, you have options.
- **SSML Support for Control**: You can use special codes called SSML to control exactly how the speech sounds. This allows for things like emphasizing certain words, adding pauses, or changing the tone of voice.

# Exploring Amazon Polly
1. Login to your AWS management console and search for Amazon Polly on the search bar.

   ![Screenshot 2024-08-16 184424](https://github.com/user-attachments/assets/26126da9-3ff0-4fb3-9ec5-0e825f315f13)

   ![11](https://github.com/user-attachments/assets/900c52d9-b64b-4611-aea3-1061e0c75173)

2. Amazon Polly offers various engines to meet different audio needs:

- **Neural Engine**: Delivers lifelike and expressive speech, ideal for natural-sounding interactions.
- **Standard Engine**: Provides clear and good quality speech suitable for a wide range of applications.
- **Long Form Engine**: Optimized for longer texts, like articles or books, ensuring consistent quality throughout.
- **Generative Engine**: Produces the most expressive and adaptive speech using Generative AI.

3. Amazon Polly supports a variety of languages and voice tones, allowing you to choose the most suitable voice tone for your application based on your needs.

   ![Screenshot 2024-08-16 185204](https://github.com/user-attachments/assets/2cf565eb-b696-4e52-82a6-6b43cac0ea75)

   ![Screenshot 2024-08-16 185346](https://github.com/user-attachments/assets/5f26be4b-82ac-43b0-bc71-17d6d5f5f69d)

4. Choose the language and voice model, type the content you want to be translated in the audio form in the input text box.

5. You can listen to the output using the Listen button present on the top right or you can even download the audio or save it in a S3 bucket.

We’ve seen a brief demo of how Amazon Polly works. In the upcoming sections, we will explore how to use a serverless function to interact with the Polly service.   
   

 
   



