# detect_labels function

Now, let's define a function called `detect_labels`. This function will take a photo and the bucket name as input parameters. Within the function:
* We create a Rekognition client using boto3.
* We use the detect_labels method of the Rekognition client to detect labels in the given photo.
* We print the detected labels along with their confidence levels.
* We load the image from the S3 bucket using boto3 and PIL.
* We use matplotlib to display the image and draw bounding boxes around the detected objects.
