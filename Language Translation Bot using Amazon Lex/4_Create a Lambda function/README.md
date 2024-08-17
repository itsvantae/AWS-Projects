# Creating a Lambda function
1. From your AWS management console, search for Lambda from your search bar.
2. Click on Create Function. Give the function a suitable name and choose the runtime as Python 3.12.
3. Choose the previously created role by toggling the default execution role option. Keep the rest of the values as default and ‘Create Function’.
4. Let us first look at the Lambda code and we will understand the code below:

   ```
   import boto3

   def lambda_handler(event, context):
       try:
           input_text = event['sessionState']['intent']['slots']['text']['value']['interpretedValue'].strip()
           language_slot = event['sessionState']['intent']['slots']['language']['value']['interpretedValue']

           if not input_text:
               raise ValueError("Input text is empty.")

           language_codes = {
               'French': 'fr',
               'Japanese': 'ja',
               'Chinese': 'zh',
               'Spanish': 'es',
               'German': 'de',
               'Norwegian': 'no'
           }


           if language_slot not in language_codes:
               raise ValueError(f"Unsupported language: {language_slot}")

           target_language_code = language_codes[language_slot]

           # Initialize the Amazon Translate client
           translate_client = boto3.client('translate')

           # Call Amazon Translate to perform translation
           response = translate_client.translate_text(
               Text=input_text,
               SourceLanguageCode='auto',  # Auto-detect source language
               TargetLanguageCode=target_language_code
           )

           translated_text = response['TranslatedText']

           lex_response = {
               "sessionState": {
                 "dialogAction": {
                     "type" : "Close"
                  },
                  "intent" : {
                    "name" : "TranslateIntent", #Add your Intent Name
                    "state" : "Fulfilled"
                  }
                },
                "messages": [
                    {
                        "contentType": "PlainText",
                        "content": translated_text
                    }
                 ]
           }

           return lex_response

      except Exception as error:
          error_message = "Lambda execution error: " + str(error)
          print(error_message)
          lex_error_response = {
              "sessionState": {
                "dialogAction": {
                    "type" : "Close"
                 },
                 "intent" : {
                   "name" : "TranslateIntent",
                   "state" : "Fulfilled"
                 }
               },
               "messages": [
                   {
                       "contentType": "PlainText",
                       "content": error_message
                   }
               ]
          }

          return lex_error_response
    ```
a) boto3 is used to interact with AWS services through code.
b) Get Input:
   ```
   input_text = event['sessionState']['intent']['slots']['text']['value']['interpretedValue'].strip()
   language_slot = event['sessionState']['intent']['slots']['language']['value']['interpretedValue']
  ```
  In this code, the user's input text and the target language are extracted from the Lex event. If you've used different slot names than those specified in this 
  documentation, be sure to update the code to match your chosen names.

c) Language codes:  
   ```
   language_codes = {
            'French': 'fr',
            'Japanese': 'ja',
            'Chinese': 'zh',
            'Spanish': 'es',
            'German': 'de',
            'Norwegian': 'no'
   }
   ```

   These are the language codes format used by Amazon Translate to identify the language to be used. We need to pass this language_code in the translate_text 
   function to translate the input according to the mapped value of the language code.

   You can further add more languages as you prefer, however remember to also add them in the slot type language.

d) Check Input:
   ```
   if not input_text:
       raise ValueError("Input text is empty.")

   if language_slot not in language_codes:
        raise ValueError(f"Unsupported language: {language_slot}")
   ```

   These lines ensure that the input text is not empty and that the target language is supported.

e) Translate:
   ```
   response = translate_client.translate_text(
       Text=input_text,
       SourceLanguageCode='auto',  # Auto-detect source language
       TargetLanguageCode=target_language_code
   )
   translated_text = response['TranslatedText']
  ```

   This section uses Amazon Translate to translate the input text into the target language specified by the user.

f) Prepare Response:
   ```
   lex_response = {
    "sessionState": {
        "dialogAction": {
            "type": "Close"
        },
        "intent": {
            "name": "TranslateIntent", #Add your intent name
            "state": "Fulfilled"
        }
    },
    "messages": [
        {
            "contentType": "PlainText",
            "content": translated_text
        }
    ]
}
```
   After translation, the code constructs a response for the chatbot with the translated text.













