# Hand-Gestures-Data-Collection-code
It helps collecting hand gestures data set efficient and easily, it uses media pipe to track hands. 
Hand Gesture Data Collection using OpenCV and cvzone
Overview

This script captures hand gestures using a webcam and saves processed images for dataset creation. It uses OpenCV for image processing and the cvzone.HandTrackingModule for hand detection.

Requirements

Ensure you have the following installed:

Python 3.x

OpenCV (cv2)

NumPy

cvzone

A webcam

Install dependencies using:

pip install opencv-python numpy cvzone

How It Works

Captures video from the webcam.

Detects a single hand using cvzone.HandTrackingModule.

Extracts the hand region and resizes it to a fixed size (300x300 pixels).

Creates a white background image and places the resized hand region on it.

Displays the real-time webcam feed with mirrored view for better usability.

Saves the processed hand image to the specified folder when the 'l' key is pressed.

Code Breakdown

cap = cv2.VideoCapture(0): Initializes webcam capture.

detector = HandDetector(maxHands=1, detectionCon=0.9): Detects a single hand with high confidence.

imgCrop: Extracts the bounding box region of the detected hand.

imgWhite: Creates a white background and places the resized hand image.

cv2.imshow('image', cv2.flip(img, 1)): Displays the flipped webcam feed.

cv2.imwrite(f'{folder}/Image_{time.time()}.jpg', imgWhite): Saves the processed image when 'l' is pressed.

Usage

Run the script:

python script.py

Position your hand in front of the webcam.

Press 'l' to capture and save the processed hand image.

Images are saved in the data/E directory with a timestamped filename.

Notes

Modify folder="data/E" to change the save directory.

The script automatically resizes and aligns hand images to a fixed size for consistency.

Ensure the data/E folder exists before running the script.
