# Real-time-multi-person-pose-estimation-and-tracking-system
# Real-Time Multi-Person Pose Estimation and Tracking System

This project implements a **real-time multi-person pose estimation and tracking system** using the MoveNet model from TensorFlow Hub. The system can detect and track the poses of up to six people simultaneously using a webcam.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [References](#references)

## Overview

The project leverages **MoveNet Multipose**, a state-of-the-art pose estimation model developed by Google, to detect keypoints of multiple people in real-time. The model is optimized for speed and accuracy, making it suitable for real-time applications on consumer hardware.

The system detects 17 key points for each person and draws both keypoints and skeleton connections in real time using OpenCV.

## Features

- Real-time pose estimation for up to 6 people.
- Draws keypoints (joints) and skeleton connections (limbs).
- Customizable confidence threshold for keypoint detection.
- Works with any webcam or video input supported by OpenCV.

## Requirements

- Python 3.6+
- TensorFlow
- TensorFlow Hub
- OpenCV
- NumPy
  
## How It Works
**MoveNet Model**:
This system uses the MoveNet Multipose Lightning model from TensorFlow Hub, which is a lightweight pose detection model optimized for real-time performance. The model outputs keypoint coordinates for 17 body parts (e.g., shoulders, elbows, knees) along with confidence scores.

**Keypoint Detection**: 
Each detected keypoint is drawn as a small green circle if its confidence score exceeds the threshold. Limbs are drawn as red lines connecting related keypoints (e.g., shoulders to elbows).

**Video Capture**: 
The system uses OpenCV to capture video frames from the webcam. Each frame is processed by the MoveNet model, and the detected poses are rendered onto the frame before being displayed.

## Results

The real-time multi-person pose estimation and tracking system performs efficiently in various scenarios with the following results:

1. **Accurate Pose Detection**: 
   - The system successfully detects up to 6 people in real-time, identifying 17 keypoints (joints) for each person (e.g., elbows, knees, shoulders).
   - Keypoints are drawn as green circles, and connections (skeleton limbs) are drawn as red lines.

2. **Real-Time Performance**: 
   - The MoveNet Multipose Lightning model provides fast and accurate pose estimation, achieving near real-time frame rates (around 15-30 FPS) depending on the system's hardware capabilities. The model is lightweight, allowing for responsive and low-latency tracking even on devices with limited computing power.

3. **Robust to Variations**:
   - The system works well in environments with multiple people, different lighting conditions, and varying body poses.
   - It is capable of estimating poses for people in complex interactions such as sitting, standing, walking, or exercising.

4. **Adjustable Confidence Threshold**:
   - The system allows for adjusting the confidence threshold to ensure higher accuracy, minimizing false keypoint detections, especially in noisy environments or when the person is partially occluded.

5. **Visual Output**: 
   - The system visually overlays keypoints and skeletons on the camera feed, making it easy to interpret pose estimations.
   - The keypoints and connections are updated in real-time as people move through the frame.
     

### Performance Metrics

- **FPS (Frames Per Second)**: On a standard laptop or desktop CPU, the system can process 15-30 frames per second, making it suitable for real-time use.
- **Latency**: The system exhibits low latency, meaning pose estimations are displayed with minimal delay from live video input.

### Limitations

- **Occlusions**: The system may struggle with partial occlusions, where one person’s body blocks another person’s keypoints, leading to reduced accuracy.
- **Low-Light Conditions**: Performance may decrease in poorly lit environments, as the model relies on visual input for keypoint detection.

### Future Improvements

- **Enhanced Occlusion Handling**: Future versions can explore techniques like depth sensors or more sophisticated occlusion detection.
- **Mobile Compatibility**: Optimizing the system for mobile or embedded devices could expand its usage across different platforms.
