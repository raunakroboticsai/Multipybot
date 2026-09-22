# 🤖 MULTIPY BOT

**One Controller PCB — Multiple Robotics Applications**

MULTIPY BOT is a modular educational robotics platform built around a single custom controller PCB. Instead of building new hardware for every robotics experiment, students reprogram the *same* board — motor control, Bluetooth, distance sensing, light sensing, temperature monitoring, servo control, buzzer, and LEDs are all onboard — to create 8+ different robot applications.

<p align="left">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Arduino%20Nano-00979D?logo=arduino&logoColor=white">
  <img alt="Status" src="https://img.shields.io/badge/status-prototype-yellow">
  <img alt="Applications" src="https://img.shields.io/badge/robot%20applications-8%2B-blue">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-green">
</p>

---
<img width="1536" height="1024" alt="Multipybot" src="https://github.com/user-attachments/assets/279b1532-e98b-4044-8f94-0abdb8fb0c3f" />


## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Robot Applications](#robot-applications)
- [Hardware Architecture](#hardware-architecture)
- [Bill of Materials](#bill-of-materials)
- [Technology Stack](#technology-stack)
- [Educational Capabilities](#educational-capabilities)
- [Development Concept](#development-concept)
- [Project Status](#project-status)
- [Getting Started](#getting-started)
- [License](#license)

---

## Overview

MULTIPY BOT is a modular educational robot platform designed to demonstrate multiple robotics concepts using a single custom controller PCB. The platform combines motor control, Bluetooth communication, distance sensing, light sensing, temperature monitoring, servo control, buzzer alerts, and LED indication — all on one board.

The same hardware platform can be programmed for different robotic applications simply by changing the firmware and robot configuration — no rewiring, no new PCB.

The goal of MULTIPY BOT is to provide a reusable, modular robotics platform for students, educators, and robotics enthusiasts — letting users start with basic motor control and progress toward sensor-based, fully autonomous robots without ever replacing the main controller PCB.

## Key Features

- 🧠 Arduino Nano 3.0 (ATmega328P) based controller
- ⚙️ Dual DC motor control via TB6612 motor driver
- 📶 HC-05 Bluetooth communication
- 📏 IR-based distance sensing
- 🎯 Servo-controlled sensor positioning
- 💡 Light intensity sensing (photocell)
- 🌡️ Temperature measurement (LM35)
- 🔊 Buzzer for audio indication
- 🔴🟢 Dual-color LED indicators
- 🔋 Battery/power monitoring interface
- 🧩 Compact, modular controller architecture
- 💻 Fully programmable through the Arduino ecosystem
- 🎓 Suitable for multiple educational robotics projects

## Robot Applications

One controller PCB, reprogrammed into eight different robots:

| # | Robot Application | Main Components |
|---|---|---|
| 01 | Bluetooth Controlled Robot | HC-05 + Arduino Nano + TB6612 |
| 02 | Obstacle Avoiding Robot | IR Distance Sensor + Servo + Motors |
| 03 | Light Following Robot | Photocell + Motors |
| 04 | Light Avoiding Robot | Photocell + Motors |
| 05 | Autonomous Explorer Robot | IR Sensor + Servo + Motors |
| 06 | Smart Patrol Robot | IR Sensor + Servo + Buzzer + LEDs |
| 07 | Temperature Monitoring Robot | LM35 + HC-05 |
| 08 | Multi-Sensor Smart Robot | IR + LDR + LM35 + Bluetooth + Servo |

## Hardware Architecture

```
                 ┌──────────────────────┐
                 │    ARDUINO NANO      │
                 │      ATmega328P      │
                 └──────────┬───────────┘
                            │
       ┌────────────────────┼────────────────────┐
       │                    │                    │
       ▼                    ▼                    ▼
  TB6612 Motor          HC-05 Bluetooth      Sensors
     Driver                  │             ┌────┼────┐
       │                     │             │    │    │
   ┌───┴───┐                 │            IR   LDR  LM35
   │       │                 │
Motor L  Motor R          Smartphone
                            │
                 ┌──────────┴──────────┐
                 │                     │
               Servo                 Buzzer
                 │
          Sensor positioning
```

## Bill of Materials

### Controller & Electronics

| Component | Reference | Qty |
|---|---|---|
| Arduino Nano 3.0 | U2 | 1 |
| TB6612 Motor Driver Module | U1 | 1 |
| HC-05 Bluetooth Module | U5 | 1 |
| POLOLU-791 Module | U3 | 1 |
| LM35DZ Temperature Sensor | U4 | 1 |
| Photocell | FTR1 | 1 |
| BC337 Transistor | Q1 | 1 |
| PK-12N40PAQ Buzzer | SG1 | 1 |
| 5 mm Bi-color LED | D1, D2 | 2 |
| Slide Switch | S1 | 1 |

### Connectors

| Connector | Reference | Qty |
|---|---|---|
| 3-Pin Connector | X4, X5 | 2 |
| 2-Pin Connector | X2, X3 | 2 |
| 4-Pin Connector | X1 | 1 |

### Passive Components

| Component | Reference | Qty |
|---|---|---|
| 10 kΩ Resistor | R1, R2, R7 | 3 |
| 4.7 kΩ Resistor | R6 | 1 |
| 10 Ω Resistor | R5 | 1 |
| 1.2 kΩ Resistor | R8 | 1 |
| 2.2 kΩ Resistor | R9 | 1 |
| Resistor, 5% 1/4 W | R3, R4 | 2 |
| 1 µF Electrolytic Capacitor | C1 | 1 |
| 100 nF Polyester Capacitor | C2 | 1 |

## Technology Stack

| Layer | Choice |
|---|---|
| Microcontroller | Arduino Nano / ATmega328P |
| Motor Driver | TB6612FNG |
| Wireless Communication | HC-05 Bluetooth |
| Temperature Sensor | LM35DZ |
| Distance Sensor | IR distance sensor |
| Light Sensor | Photocell / LDR |
| Actuator | Servo Motor |
| Programming Platform | Arduino IDE |

## Educational Capabilities

MULTIPY BOT can be used to teach:

- Embedded Systems
- Arduino Programming
- Motor Control & PWM
- Bluetooth Communication
- Sensor Interfacing & Analog Data Acquisition
- Autonomous Navigation & Obstacle Detection
- Light-Based Robotics
- Temperature Sensing
- Servo Motor Control
- Basic Robotics Algorithms
- IoT and Wireless Communication concepts

## Development Concept

The main concept behind MULTIPY BOT is **hardware reuse through software programming**.

Instead of requiring a separate controller for every robotics experiment, students use the same PCB and build different applications by changing the program and robot configuration.

```
              MULTIPY BOT PCB
                     │
       ┌─────────────┼─────────────┐
       │             │             │
   Bluetooth      Sensors      Autonomous
     Robot          Robot        Robot
       │             │             │
       ▼             ▼             ▼
   Different     Different     Different
   Firmware      Firmware      Firmware
```

Users start with basic motor control and progress toward sensor-based and fully autonomous robotic applications — without ever replacing the main controller PCB.

## Project Status

| | |
|---|---|
| **Hardware** | PCB-based prototype |
| **Platform** | Modular educational robotics system |
| **Applications** | 8+ programmable robot configurations |

## Getting Started

1. Clone this repository
2. Assemble the MULTIPY BOT PCB per the [Bill of Materials](#bill-of-materials)
3. Open the desired robot application's firmware in the Arduino IDE
4. Flash it to the Arduino Nano
5. Power on and run the selected robot application

> Detailed per-application wiring diagrams and firmware are organized under `/firmware` and `/hardware` (add your project folders here).

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

<p align="center"><i>MULTIPY BOT — One Controller PCB, Multiple Robotics Applications.</i></p>
