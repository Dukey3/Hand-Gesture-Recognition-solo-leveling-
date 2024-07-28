# Hand-Gesture-Recognition-solo-leveling-
#This is my Foss hack 2024 submission

Hand Gesture Recognition

This repository contains the following contents:-
1.Hand sign recognition model(TFLite)
2.Finger gesture recognition model(TFLite)
3.Learning data for hand sign recognition and notebook for learning.
4.Learning data for finger gesture recognition and notebook for learning.
5.Required utilities.
6.TK frontend


Requirements:-

1.mediapipe 0.8.1
2.OpenCV 3.4.2 or Later
3.Tensorflow 2.3.0 or Later
4.tf-nightly 2.5.0.dev or later (Only when creating a TFLite for an LSTM model)
5.scikit-learn 0.23.2 or Later (Only if you want to display the confusion matrix)
6.matplotlib 3.3.2 or Later (Only if you want to display the confusion matrix
7.Argparse
8.ConfigParser
9.itertools
10.Copy
11.Collections: For specialized data structures like deque and Counter.

Directory:-

│
├── config.ini                             # Configuration file
├── main_script.py                         # Main script (the provided code)
├── utils/
│   ├── CvFpsCalc.py                       # Utility for FPS calculation
│   └── other_util_files.py                # Other utility files
├── model/
│   ├── KeyPointClassifier/
│   │   ├── keypoint_classifier.py         # KeyPoint Classifier model file
│   │   ├── keypoint_classifier_label.csv  # Labels for KeyPoint Classifier
│   │   └── keypoint.csv                   # Logged data for KeyPoint Classifier
│   ├── PointHistoryClassifier/
│   │   ├── point_history_classifier.py    # Point History Classifier model file
│   │   ├── point_history_classifier_label.csv # Labels for Point History Classifier
│   │   └── point_history.csv              # Logged data for Point History Classifier
│   └── other_model_files.py               # Other model-related files
└── other_project_files.py                 # Other files related to the project





Training:- same as the original code.


Key Differences and Improvements:

Configuration Handling:

Source Code: Uses command-line arguments for configuration.

My Code: Utilizes a config.ini file, allowing for easier and more flexible configuration management without modifying the code.

Logging and Data Saving:

Source Code: Handles data logging directly, with less modularity.

My Code: Implements a logging_csv function, making the logging process more organized and modular, which is beneficial for maintenance and scalability.

Functions and Modularity:

Source Code: Functions like draw_info_text and draw_landmarks are more integrated into the main code body.

My Code: More modular and separate functions, improving readability and maintainability. This also aids in debugging and extending the codebase.

Additional Features:

My Code: Adds more detailed visual feedback, such as enhanced bounding rectangle displays and point history visualization. Also, additional information like mode and logging status is displayed on the screen.

Error Handling and Robustness:
Source Code: Less focus on comprehensive error handling.

My Code: More robust error handling, including checks for the availability of classes like mp_hands.Hands and handling file operation issues.
Code Structure and Flow:

Source Code: Simpler structure, potentially easier for smaller scripts but less scalable.
My Code: More organized, with distinct sections for loading configurations, initializing components, processing frames, and handling user inputs, making it more suitable for complex applications.

Visualization Enhancements:

My Code: Includes more comprehensive visualization, with detailed rendering of landmarks and other visual cues.

Explination:-

app.py


This is a sample program for inference.
In addition, learning data (key points) for hand sign recognition,
You can also collect training data (index finger coordinate history) for finger gesture recognition.

keypoint_classification.ipynb

This is a model training script for hand sign recognition.

point_history_classification.ipynb

This is a model training script for finger gesture recognition.

model/keypoint_classifier
This directory stores files related to hand sign recognition.
The following files are stored.

Training data(keypoint.csv)
Trained model(keypoint_classifier.tflite)
Label data(keypoint_classifier_label.csv)
Inference module(keypoint_classifier.py)
model/point_history_classifier
This directory stores files related to finger gesture recognition.
The following files are stored.

Training data(point_history.csv)
Trained model(point_history_classifier.tflite)
Label data(point_history_classifier_label.csv)
Inference module(point_history_classifier.py)
utils/cvfpscalc.py
This is a module for FPS measurement.



Pros and Cons:

My Code:
Pros:

Modular: Functions are well-separated, improving code readability and maintainability.
Comprehensive Feature Set: Includes additional features and detailed logging capabilities.
Robust Error Handling: More checks and error handling mechanisms.

Cons:
Complexity: More complex due to additional functions and configuration management.
Extra Setup: Requires setting up a config.ini file, which might be an extra step for users.

Source Code:
Pros:

Simplicity: Easier to understand due to straightforward implementation.
Flexible Configuration: Command-line arguments provide flexibility in managing configurations.

Cons:
Less Modular: Fewer separations of concerns, potentially making it harder to maintain and extend.
Limited Error Handling: Less comprehensive handling of potential issues.

In summary, "My Code" offers a more feature-rich, modular, and robust implementation, suitable for comprehensive applications.
 In contrast, the original "Source Code" is simpler and more straightforward, making it ideal for quick prototyping or smaller projects.
 The choice between the two depends on the specific needs and complexity of the project.
