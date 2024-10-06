# Driveway Camera and Alerts Setup

## Development Status

This project is currently in **development**. The repository contains the shell structure, including named but empty files, with plans to implement the full functionality soon.

## Project Overview

This project is a driveway monitoring system using Raspberry Pi devices for real-time object detection and smart alerting. The system is designed to detect people in the driveway and vehicles arriving or departing from the driveway. Additionally, the system monitors vehicles stopping at the mailbox.

Object detection is powered by the YOLOv10 algorithm, providing high-accuracy detection for vehicles and people. Once an object is detected, LLaMA is used to generate intelligent, context-aware alerts, which are sent to your phone via Pushover.

### Hardware Setup:

#### 1. **Pi Zero 2 W**
   - **Role**: Handles video control, camera selection, light measurement, and pushes the video stream to the server.
   - **Components**:
     - **Daytime Camera**: Arducam HQ 12.3 MP
     - **Nighttime Camera**: Pi NoIR Camera Module V2 - 8 MP
     - **Light Sensor**: CQRobot TSL25911FN (for automatic day/night detection)
     - **Doubleplexer**: Arducam Doubleplexer Stereo Module V2 (for switching between the daytime and nighttime cameras)

#### 2. **Pi 4**
   - **Role**: Performs the main processing, including image analysis with YOLOv10, and sends alerts to your phone using LLaMA (for formatting) and Pushover (for notifications).