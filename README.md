# STM32 Desktop Robotic Manipulator

A desktop robotic manipulator controlled by an STM32 microcontroller, designed to pick up and move lightweight objects between predefined positions.

## Project Design

The robotic manipulator is being designed in Autodesk Fusion 360.

<p align="center">
  <img
    src="https://github.com/user-attachments/assets/4645297b-01e9-4a66-bc2b-a9fbdeb0bbc7"
    alt="Robotic Manipulator — Fusion 360 Model"
    width="480"
  />
</p>

## Team Members and Responsibilities

| Team Member | Development Area | Main Responsibilities |
|---|---|---|
| **Daniil Komarnytskyi** | Hardware & Servo Drivers | STM32 configuration, PWM generation, timer setup, I²C communication, and servo motor drivers. Also responsible for the KiCad electrical schematic, power distribution, and electrical component selection. |
| **Danylo Lysenko** | Motion Control & Automation | Smooth servo movements, motion interpolation, Manual/Auto operating modes, automated movement sequences, and Teach & Repeat functionality. |
| **Artem Kovalenko** | Robot Kinematics | Forward and inverse kinematics, the manipulator's geometric model, and joint limits. Also responsible for mechanical design and 3D modeling in Autodesk Fusion 360. |
| **Renat Moskalenko** | Embedded Communication & Desktop Analytics | Embedded C development for high-frequency telemetry (DAQ), asynchronous DMA-based USART communication, and secure binary command protocols on the STM32. Also responsible for the desktop engineering application used for real-time data visualization, live controller tuning, and manipulator control. |

All team members will cooperate during assembly, firmware integration, testing, debugging, and final evaluation of the robotic manipulator.

## Hardware

- **STM32 NUCLEO-F303K8** — main controller.
- **2× SG90 servo motors** — manipulator movement.
- **3× MG996R 270° servo motors** — robotic arm movement.
- **1× 5 V, 20 A switching power supply** — dedicated power supply for the servo motors.
- **6× Panel-mounted 5×20 mm fuse holders with screw caps** — for installing a 10 A fuse to protect the power circuit.

## Servo Power Distribution

The following schematic, designed using KiCad, illustrates the planned servo motor connections, PWM control signals and dedicated power supply.

**Servo Power Distribution Schematic**

<p align="center">
  <img
    src="https://github.com/user-attachments/assets/263637c7-a87a-47cd-a4b7-2def0fbda4ca"
    alt="Servo Power Distribution Schematic"
    width="500"
  />
</p>

The servo motors will be powered by a dedicated 5 V power supply, separate from the USB power supplied to the STM32 Nucleo board.

- **+5V_SERVO** — dedicated 5 V power supply for the servo motors.
- **GND** — common ground between the servo power supply and the control system.
- **SERVO1_PWM – SERVO5_PWM** — PWM control signals from the STM32 Nucleo board or an external servo controller, depending on the final design.
- **USB power** — powers the STM32 Nucleo board independently of the servo power supply.
- **10 A fuse** — planned overcurrent protection for the servo power circuit.

The fuse rating, wiring and connectors will be verified against the expected servo current and the electrical ratings of the components before assembly.

## Planned Features

- Manual control of the robotic arm from a computer.
- Automatic movement sequences for picking up and transferring objects.
- Teaching and saving predefined positions.
- Smooth servo movements.
- Evaluation of positioning accuracy, repeatability and object transfer success rate.

## Communication

- **I²C** — planned communication between the STM32 and an external servo controller, if used.
- **USART** — communication between the computer and the STM32 for transmitting control commands and joint position values.

The communication hardware and software will be selected and implemented during development.

## Missing Components

The following document contains the current list of components that still need to be purchased to complete the project:

[**Microsoft Word Document — Missing Components and Purchase List**](https://github.com/user-attachments/files/34935506/Microsoft.Word.Document.docx)

## Project Goal

The goal is to build a functional, programmable robotic manipulator that can perform repeatable object transfer tasks. As an optional extension, we may implement simple inverse kinematics or object detection.

The project will be evaluated through practical experiments measuring positioning accuracy, repeatability and successful object transfers.
