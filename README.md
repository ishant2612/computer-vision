# Hand Detection and Volume Control Project

## Overview
This project consists of two main modules: 
1. `handdetectorModule.py` - A Python module for hand detection using MediaPipe.
2. `volumeControl.py` - A script to control the system volume based on hand gestures using the hand detection module.

## Installation

### Prerequisites
- Python 3.x
- pip (Python package installer)

### Required Libraries
The project requires several Python libraries. You can install them using `pip`.

```sh
pip install opencv-python mediapipe numpy comtypes pycaw


Files Description
handdetectorModule.py
This module contains the handDetector class that utilizes MediaPipe to detect hands and finger positions in a video stream.

handDetector Class Methods
__init__(self, mode=False, maxHands=2, detectionCon=0.5, trackCon=0.5): Initializes the hand detector with the given parameters.
findHands(self, img, draw=True): Processes the input image to find hands and optionally draws the hand landmarks.
findPosition(self, img, handNo=0, draw=True): Finds the positions of the hand landmarks and returns a list of them along with the bounding box.
fingersUp(self): Checks which fingers are up and returns a list indicating the state of each finger.
findDistance(self, p1, p2, img, draw=True): Finds the distance between two points on the hand and optionally draws the connecting line.
Running the Module
To run the handdetectorModule.py independently and see hand detection in action:

sh
Copy code
python handdetectorModule.py
volumeControl.py
This script uses the handDetector class from handdetectorModule.py to control the system volume based on hand gestures.

Key Functions
Captures video from the webcam.
Detects the hand and its landmarks.
Measures the distance between the thumb and index finger to determine the volume level.
Adjusts the system volume using Pycaw based on the distance.
Running the Script
To run the volumeControl.py script:

sh
Copy code
python volumeControl.py
Usage
Hand Detection:

Run handdetectorModule.py to see the real-time hand detection. Adjust the camera if needed.
Hand landmarks will be displayed on the screen along with the FPS (Frames Per Second).
Volume Control:

Run volumeControl.py.
Use your thumb and index finger to control the volume. The distance between these fingers will determine the volume level.
Ensure the webcam is functioning and properly positioned to capture your hand movements.
Notes
Ensure that your environment has good lighting for better hand detection accuracy.
The default camera index in volumeControl.py is set to 1. If you have only one webcam, change cv2.VideoCapture(1) to cv2.VideoCapture(0).
License
