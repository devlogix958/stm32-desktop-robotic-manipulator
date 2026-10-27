# STM32 Desktop Robotic Manipulator

A desktop robotic manipulator controlled by an STM32 microcontroller, designed to pick up and move lightweight objects between predefined positions.

## Project Design

The robotic manipulator is being designed in Autodesk Fusion 360.

![Robotic Manipulator — Fusion 360 Model](https://github.com/user-attachments/assets/4645297b-01e9-4a66-bc2b-a9fbdeb0bbc7)

## Hardware

- **STM32 NUCLEO-F303K8** — main controller
- **2× SG90 servo motors** — movement of the manipulator
- **3× MG996R 270° servo motors** — movement of the robotic arm
- **2× 5 V, 6 A power supplies** — servo power supply

## Servo Power Distribution

The following schematic shows the servo motor connections, PWM control signals and separate power supply for the servos.

**Servo Power Distribution Schematic**

<img width="1280" height="796" alt="image" src="https://github.com/user-attachments/assets/3bcf117f-506e-4e0c-bf79-74e0ae4d4f52" />

The servo motors are powered by a dedicated 5 V power supply, separate from the USB power supplied to the STM32 Nucleo board.

- **+5V_SERVO** — dedicated 5 V power supply for the servo motors.
- **GND** — common ground for the servo power supply and control signals.
- **SERVO1_PWM – SERVO5_PWM** — PWM control signals from the STM32 Nucleo board.
- **USB power** — powers the STM32 Nucleo board independently of the servo power supply.

## Planned Features

- Manual control of the robotic arm from a computer.
- Automatic movement sequences for picking up and transferring objects.
- Teaching and saving predefined positions.
- Smooth servo movements.
- Evaluation of positioning accuracy, repeatability and object transfer success rate.

## Communication

- **I²C** — planned communication interface for servo control, potentially using an external servo controller.
- **USART** — communication between the computer and the STM32 for transmitting control commands and joint position values.

The communication hardware and software will be selected and implemented during development.

## Missing Components

The following document contains the current list of components that still need to be purchased to complete the project:

[**Microsoft Word Document — Missing Components and Purchase List**](https://github.com/user-attachments/files/33992098/Microsoft.Word.Document.docx)

## Project Goal

The goal is to build a functional, programmable robotic manipulator that can perform repeatable object transfer tasks. As an optional extension, we may implement simple inverse kinematics or object detection.

The project will be evaluated through practical experiments measuring positioning accuracy, repeatability and successful object transfers.
