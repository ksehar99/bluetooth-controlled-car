# Bluetooth-Controlled Car Using Arduino

## Introduction

This project demonstrates how to control a robot using an **Arduino board** with an ultrasonic sensor for obstacle detection and a motor driver for motor control. The robot can move forward, backward, left, right, and stop based on commands received via Bluetooth.

## Components Used

- Arduino Uno
- Motor Driver (L293D)
- Bluetooth Module (HC-05)
- Ultrasonic Sensor (HC-SR04)
- 4WD Robo Car Chassis
- DC Motors (4)
- Buzzer
- Mini Breadboard
- Green LED
- Red LED
- Few resistors
- 12V Battery

## Libraries Required

- **AFMotor**: For controlling DC motors via the motor driver.
- **NewTone**: For generating tones on the buzzer.

You can install these libraries via the Arduino Library Manager.

## Pin Configuration

- **Ultrasonic Sensor**
  - Trigger Pin: A1
  - Echo Pin: A0
- **LEDs**
  - Green LED: A3
  - Red LED: A4
- **Buzzer**
  - Buzzer: A5
- **Bluetooth Module**
  - Connected to Arduino's RX/TX pins (to upload the code to the Arduino)

## How It Works

1. **Distance Measurement**: The ultrasonic sensor measures the distance to an object.
2. **Movement Control**: Based on the distance:
   - If the distance is greater than 20 cm, the robot listens for serial commands sent via Bluetooth.
   - Commands are sent from the Arduino BlueControl app, which connects to the Arduino via a Bluetooth module.
   - The Bluetooth module receives these commands and sends them to the Arduino through the serial interface.
   - The Arduino processes the commands and controls the robot's movements accordingly.
   - If the distance is 20 cm or less, the robot performs obstacle avoidance behavior by backing up, turning right, and then moving forward.
3. **Commands**:
   - `F`: Move forward
   - `B`: Move backward
   - `L`: Turn left
   - `R`: Turn right
   - `S`: Stop all motors
   - `H`: Sound the horn (buzzer)

## Usage

1. **Upload the Code**:
   - Open the Arduino IDE and load the `Code` file.
   - Disconnect the Bluetooth module from the Arduino before uploading the code to prevent interference.
   - Upload the code to your Arduino board.

2. **Reconnect the Bluetooth Module**:
   - After uploading the code, reconnect the Bluetooth module to the Arduino.

3. **Control the Robot**:
   - Open the Arduino BlueControl app on your mobile device and pair it with the Bluetooth module.
   - Use the app to send commands to the Arduino (e.g., `F`, `B`, `L`, `R`, `S`, `H`).

## Acknowledgments

- The Arduino BlueControl app is used for Bluetooth communication.
- The L293D motor driver is used for controlling the DC motors.
- The HC-SR04 ultrasonic sensor is used for obstacle detection.
- The **AFMotor** library is used for controlling the DC motors.

