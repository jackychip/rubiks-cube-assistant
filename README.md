# Rubik’s Cube Assistant (WIP) – Jacky Zhang

## Introduction

The Rubik’s Cube Assistant is a smart tool that helps you solve your 3x3x3 Rubik’s Cube. With a camera, the assistant can analyze the colours and positions of the pieces, and give the user clear step-by-step instructions to solve the cube. Whether you’re a beginner or looking for improvement, this assistant makes the process simple and fun.

## Materials and Dependencies

**OV-7670 Camera Module**: A VGA camera module with a CMOS (low power circuit) image sensor that provides 8-bit images.

**Arduino Uno**: Another microcontroller board used to bridge USB Serial communication to the ESP32-CAM without an FTDI adapter.

**ArduImageCapture**: A Java program and Arduino plugin to translate the serial output (detected from the sensor) into pixels.

**LiveOV7670**: A C/C++ Arduino library that streamlines programming an OV7670 by providing read/write methods.

## Setup

#### DISCLAIMER: The project is a work-in-progress and some of the following steps have not been implemented.

### Installation

1. Install Arduino version 1.x (newest version doesn't support tools)

2. Install the ArduImageCapture library at `https://github.com/indrekluuk/ArduImageCapture`

    1. Download the Github project (click Code, then Download Zip).
    2. Extract the zip folder and move its contents into your `C:/...Documents/Arduino/tools`
    3. If a `tools` folder doesn't exist, create a new folder named `tools`

3. Download this Github project as a ZIP and import it into your Arduino 1.x IDE

### Running the project

1. Plug the USB into a computer port or attach an external power supply to the Arduino.
2. Under `setup.h`, ensure that `#define EXAMPLE 3` is written.
3. Click upload, then under `Tools` at the top left of your IDE, click `ArduImageCapture`.
4. Click the `Listen` button, and then wait for the camera to adjust to lighting (wait for initial brightness to turn down).
5. Follow the instructions in the terminal.
6. After processing the cube, the terminal will output a set of moves in a specific notation (use `https://ruwix.com/the-rubiks-cube/notation/` to decipher the notation).

Happy solving!

## TO-DO

- **OV7670 Camera Module**
    - Tweak with pulse clock (PCLK) and clock (XCLK) frequencies to produce a non-blurry and non-buggy video output
    - Implement colour recognition through reading bytes at a pixel
- **Algorithm**
    - Implement this library used to solve and output moves: `https://pypi.org/project/rubik-cube/`
    - Create arrays for each side of the cube as input
- **Future Endeavours**
    - Implementation of servos and 3D-printed holds to turn the cube
    - Creation of a custom video streaming application for the camera (to fit the needs of this project)