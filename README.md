# LSTM-SignLanguageConversion
> The project uses **Long Term Convolutional Neural Networks (LSTMs)** to recognize and convert sign language gestures into readable text. This project can be applied in communication support tools for the blind or people who have difficulty communicating by speech.
## Target
The goal of the project is to develop a system that can recognize sign language gestures and convert them into corresponding text. This will help create communication support tools for people who use sign language in their daily lives.
## Features
+ Sign language recognition: The system can recognize sign language gestures from videos or images.
+ Convert to text: Sign language gestures will be converted into text through the LSTM deep learning model.
+ Applications in daily communication: The project can be used to support communication for the blind or those who communicate using sign language.
## Technology
+ Programming language: Python
+ Libraries: TensorFlow / Keras, OpenCV, NumPy, Pandas, Matplotlib, scikit-learn,...
## Data
Instead of using sample data, we collect data in real time. To recognize symbols, we need to use a webcam to receive data.

```cap = cv2.VideoCapture(0)```

```success, frame = cap.read()```

Because OpenCV uses BGR color space by default, while MediaPipe usually requires RGB. So we convert from BGR image to RGB image for easy processing. Then we use the Holistic model of MediaPipe to process the image and return the results of the detected features in the image

```def mediapipe_detection(image, model):```

```image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)```

```image.flags.writeable = False```

```results = model.process(image)```

```image.flags.writeable = True```

```image = cv2.cvtColor(image, cv2.COLOR_RGB2BGR)```

```return image, results```

![example](data.jpg)

## Results
Model structure:

![example](cautruc.jpg)

Model results image:

![example](ketquamohinh.jpg)

Accurancy:

![example](danhgia.jpg)

## Future Development
+ Improve the accuracy of the model for complex sign language contexts.

+ Build an easy-to-use user interface so that users can interact directly with the sign language conversion system.

## Contact
If you have any questions or contributions about the project, please contact us via email: quangh922@gmail.com.

## License
This project is released under the **MIT License**.
