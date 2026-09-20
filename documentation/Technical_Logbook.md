# Technical Logbook - Entry 1

# Date: September 19, 2026

# Team members:
Ruben Alvarez Duran
Samantha Elena Camacho Badillo
Juan David Castruita Castañeda
Angel Daniel Cisneros Perez

# Current project status: 
System architecture defined; validation planning stage. The mechanical SCARA concept, ESP32-S3 controller, three NEMA 17 motors with A4988 drivers, limit switches, 12 V electromagnet, MOSFET switching stage, and 12 V / 6 A power architecture have been selected.

# Work completed:
Defined the embedded-system architecture; replaced the original Arduino-based concept with ESP32-S3 control; selected the electromagnet as the end effector; created the hardware/software partition, preliminary BOM, technical-risk analysis, validation KPIs, acceptance criteria, and initial test cases.

# Problems found:
The previously available 12 V / 4.5 A supply provides limited margin compared with the project requirement. The exact current rating of the final NEMA 17 motors and the holding force/current of the selected electromagnet still need to be confirmed. A4988 current limits must also be adjusted before full-load testing.

# Decisions made:
Use an ESP32-S3 as the central controller; use three NEMA 17 motors and three A4988 drivers; use a 12 V electromagnet instead of a servo gripper; specify a 12 V / 6 A supply for the final architecture; use limit switches for homing and travel limits; use USB/UART as the initial communication interface.

# Next task:
Assemble and verify the power/control electronics on the bench, configure A4988 current limits, test the limit switches and electromagnet driver, and then execute TC-01 before motion-accuracy and endurance tests.