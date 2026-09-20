# SCARA Robot Embedded System

## Project Overview
This project develops a three-axis SCARA robot controlled by an ESP32-S3. Two NEMA 17 stepper motors provide rotational motion, one NEMA 17 provides vertical Z-axis motion, and a 12 V electromagnet is used as the end effector for handling ferromagnetic parts.

## Main Hardware
- ESP32-S3 DevKitC-1
- 3 x NEMA 17 stepper motors
- 3 x A4988 stepper motor drivers
- 3 x mechanical limit switches
- 12 V electromagnet
- Logic-level N-channel MOSFET and flyback diode
- 12 V / 6 A power supply
- 12 V to 5 V buck converter

## Main Functions
- Three-axis motion control
- Homing and travel-limit detection
- Electromagnet ON/OFF control
- USB/UART communication
- Optional Wi-Fi/BLE monitoring

## Repository Structure
```text
SCARA_Validation_Project/
|
|-- hardware/
|-- firmware/
|-- documentation/
|-- tests/
|-- README.md
`-- REPOSITORY_LINK.txt
```

## Validation Strategy
The initial validation plan evaluates positioning accuracy, homing repeatability, command response latency, power consumption, operational stability, and electromagnet pick reliability. Detailed acceptance criteria and test procedures are stored in `tests/SCARA_Validation_Tables.xlsx` and `documentation/SCARA_Validation_Plan.pdf`.

## Recommended Test Order
1. Electrical inspection and power verification.
2. Homing and limit-switch validation.
3. Point-to-point positioning validation.
4. Power-consumption validation.
5. Electromagnet pick-and-place validation.
6. Continuous stability validation.

## Current Status
Architecture and validation planning are complete. Bench testing of the power stage, A4988 current limits, limit switches, and electromagnet driver is the next step.

## Safety Note
The ESP32-S3 uses 3.3 V GPIO logic. Do not apply 5 V directly to its GPIO pins. The electromagnet must be switched through a suitable MOSFET stage with flyback protection.