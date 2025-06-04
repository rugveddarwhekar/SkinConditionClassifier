# SkinConditionClassifier

## Project Overview
SkinConditionClassifier is an Android application that uses Firebase AutoML to classify skin conditions from images. The app allows users to select an image from their device, crop it, and then processes the image using a local TFLite model to predict the skin condition. The model can classify 15 different skin conditions, including Eczema, Acne, Melanoma, and more.

## Motivation
The project aims to provide a quick, on-device tool for preliminary skin condition assessment. By leveraging machine learning, it helps users identify potential skin issues without requiring immediate professional consultation, thus raising awareness and encouraging timely medical advice.

## Features
- **Image Selection & Cropping**: Users can select an image from their device and crop it for better analysis.
- **On-Device Classification**: Utilizes a local TFLite model for fast, offline skin condition classification.
- **Multiple Condition Detection**: Classifies 15 different skin conditions with confidence scores.
- **User-Friendly Interface**: Simple UI with an image preview and clear classification results.

## Architecture & Diagrams
The application follows a straightforward architecture:

```
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  User Interface  | --> |  Image Selection | --> |  Image Cropping  |
|                  |     |                  |     |                  |
+------------------+     +------------------+     +------------------+
        |                                                |
        v                                                v
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  Firebase AutoML | --> |  TFLite Model    | --> |  Classification  |
|                  |     |                  |     |                  |
+------------------+     +------------------+     +------------------+
```

### Components:
- **User Interface**: Built using Android XML layouts (`activity_main.xml`).
- **Image Selection & Cropping**: Uses the `android-image-cropper` library.
- **Firebase AutoML**: Integrates Firebase ML Kit for model management and inference.
- **TFLite Model**: A local model (`model.tflite`) bundled in the assets folder, with labels defined in `dict.txt`.

## How It Works
1. **Image Selection**: The user taps the "Select Image" button, which opens the device's image picker.
2. **Image Cropping**: The selected image is cropped using the `CropImage` library.
3. **Model Inference**: The cropped image is processed by the local TFLite model using Firebase AutoML.
4. **Classification**: The model predicts the skin condition and displays the result with a confidence score.

## Setup & Installation
1. Clone the repository.
2. Open the project in Android Studio.
3. Update `google-services.json` with your Firebase API key.
4. Build and run the application on an Android device or emulator.

## Usage
1. Launch the app.
2. Tap "Select Image" to choose an image from your device.
3. Crop the image as needed.
4. View the classification result displayed below the image.

## Learnings
- Integration of Firebase ML Kit with Android applications.
- Handling image selection and cropping in Android.
- On-device machine learning using TFLite models.

## Possible Improvements
- **Remote Model Updates**: Implement dynamic model updates from Firebase.
- **Enhanced UI**: Improve the user interface with better styling and feedback.
- **Additional Conditions**: Expand the model to classify more skin conditions.
- **Offline Support**: Ensure robust offline functionality.

## Credits
Special thanks to Firebase and the Android community for their tools and libraries.
