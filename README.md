Here is the updated `README.md` without team details:

***

# OEM‑Independent Telematics Control Unit (TCU)

OEM‑Independent Telematics Control Unit (TCU) is a simulation‑based prototype of an in‑vehicle telematics system designed to monitor critical vehicle parameters and display them directly to the driver without relying on OEM OBD‑II ports or cloud connectivity. The system targets mixed‑brand commercial fleets and legacy vehicles, offering a unified, secure, and local monitoring solution.[1]

## Project Overview

Modern fleet telematics solutions typically depend on OEM‑specific OBD‑II interfaces and cloud platforms, which can introduce vendor lock‑in, data fragmentation, security risks, and delayed feedback to drivers. This project proposes an OEM‑agnostic TCU that operates entirely within the vehicle, aggregating sensor data and presenting real‑time alerts on a driver‑facing display.[1]

### Key Features

- Real‑time Tire Pressure Monitoring System (TPMS) using BMP180 digital pressure sensor.[1]
- Engine temperature monitoring and alerting using LM35 temperature sensor model.[1]
- GPS tracking and basic geolocation using TinyGPS‑based module.[1]
- RF‑based gate/door control for V2X‑style automated gate access.[1]
- Local LCD display (16x2) for consolidated TPMS, engine temperature, and gate status information.[1]
- No cloud dependency: all data acquisition, processing, and display remain inside the vehicle network.[1]

> Note: This is currently a **simulation project** implemented and tested in Proteus 8; a full hardware build has not yet been completed.[1]

## Motivation

Fleet operators managing mixed‑brand vehicles often struggle with:[1]

- OEM lock‑in and incompatible telematics hardware across brands.  
- Separated data sets and delayed access to diagnostic information.  
- Drivers not being informed immediately about critical issues (e.g., low tire pressure, overheating).[1]

By building a local, OEM‑independent TCU, the project aims to improve safety, uptime, and fuel efficiency while enhancing data privacy and reducing reliance on external cloud services.[1]

## System Architecture

The simulated system consists of:

- **Microcontroller**: Arduino Uno R3 (ATmega328P) as central TCU controller.[1]
- **Sensors (simulated in Proteus)**:  
  - BMP180 – tire pressure sensing and alert thresholds (e.g., low pressure, over‑inflation).[1]
  - LM35 – engine temperature sensing with graded alarm states (normal, high, overheat).[1]
- **Communication & Control**:  
  - RF TX/RX modules for gate/door control and simple V2X‑style signaling.[1]
  - GPS module for position data (latitude/longitude) via TinyGPS.[1]
- **User Interface**:  
  - 16x2 LCD (LM016L) to display pressure, temperature, GPS info, and gate status.[1]
  - Buzzer/speaker output for audible alerts on abnormal conditions.[1]

All modules are wired and validated in **Proteus 8 Professional** using native and custom libraries (BMP180‑I2C, RF modules, GPS library).[1]

## Implemented Modules

1. **Tire Pressure Monitoring & Alert System**  
   - Reads simulated BMP180 pressure values.  
   - Converts to psi and categorizes into normal, low, and over‑inflated ranges with LCD text and buzzer alerts.[1]

2. **Engine Monitor System**  
   - Reads LM35 analog temperature, converts to °C.  
   - Displays temperature and triggers different audio/visual alerts for rising severity levels.[1]

3. **RF‑Controlled Gate Module**  
   - Receives distance/command values over serial/RF.  
   - Drives a servo (gate actuator) and LCD messages (“GATE IS OPENING”, “GATE CLOSED”).[1]

4. **GPS Display Module**  
   - Parses NMEA data from GPS module with TinyGPS.  
   - Shows latitude and longitude values on LCD for basic tracking.[1]

## Tech Stack

- **Languages**: C/C++ (Arduino)  
- **IDE**: Arduino IDE  
- **Simulation & Schematic Capture**: Proteus 8 Professional  
- **Core Components (simulated)**: Arduino Uno R3, BMP180, LM35, RF TX/RX modules, GPS module, 16x2 LCD, buzzer, servo.[1]

## Getting Started

1. Open the Proteus 8 project file(s) included in this repository.  
2. Ensure required libraries are installed (BMP180‑I2C, GPS module, RF modules, Arduino).[1]
3. Open the corresponding Arduino sketches in Arduino IDE and compile to generate HEX files.  
4. Attach the HEX files to the Arduino components inside Proteus and run the simulation to observe LCD outputs and alerts.[1]

## Future Work

- Build and test a full hardware prototype on‑vehicle.  
- Replace Arduino Uno with higher‑performance MCU for extended diagnostics and data logging.[1]
- Integrate additional vehicle parameters (battery health, fuel level, CAN‑based data where available).  
- Develop a more advanced driver HMI and optional secure gateway for fleet dashboards.[1]

---

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/18122254/89001919-5080-450f-966b-7aebeddefd0b/23BME017_Innovation_Brief__Proposal_Document-1.pdf)
