# electrical-engineering-projects
Electrical Engineering Projects

# Smart Beehive Monitoring System Hardware Design

## Overview

This repository documents the hardware design and prototyping work carried out for a smart beehive monitoring system.

The project's objective was to develop a distributed monitoring solution that allows beekeepers to remotely supervise the condition and status of their hives without the need for frequent on-site visits. The system collects environmental and operational data from multiple hives and transmits it to a central server through a cellular network.

In addition to hive monitoring, the system was designed to provide theft detection and asset tracking capabilities.

My responsibility within the project was the complete hardware design, electronic circuit development, PCB design, and prototype manufacturing.

---

## Project Goals

The system was designed to:

- Reduce the need for regular manual inspections.
- Provide remote access to critical hive parameters.
- Enable centralized monitoring of multiple hives.
- Store measured data locally in case of communication outages.
- Improve security through theft detection and GPS tracking.
- Support scalable deployment across larger apiaries.

---

## System Architecture

The solution consists of two hardware variants deployed throughout the apiary.

<img width="805" height="536" alt="image" src="https://github.com/user-attachments/assets/502ec182-4197-455d-882c-c9bb0e098c63" />


### Master Unit

The master unit is installed on a beehive in the same way as the slave units, but serves as the central communication gateway of the system.

In addition to performing local sensor acquisition, it is responsible for:

- Cellular communication via the 4G network
- Data transmission to the central server
- Local data logging to an SD card
- GPS positioning and asset tracking
- RS-485 communication with slave units
- Coordination of the distributed monitoring network

Main components:

- Arduino Uno
- SIM908 GSM/GPRS/GPS module
- SD card interface
- RS-485 communication interface
- 12 V battery-powered supply system

### Slave Units

Slave units are also installed on individual beehives and provide distributed sensor acquisition within the monitoring network.

Their primary role is to:

- Collect sensor data
- Perform local signal conditioning and preprocessing
- Communicate with the master unit through RS-485

Main components:

- Arduino Uno
- Sensor interfaces
- RS-485 communication interface
- Local power management circuitry

### Network Topology

Each monitored hive contains either a master or a slave unit.

The master unit collects its own local measurements while simultaneously aggregating data received from the connected slave units. The complete dataset is then stored locally on an SD card and periodically transmitted to the central server through the cellular network.

This distributed architecture enables multiple hives to be monitored using a single cellular connection. As a result, deployment and operational costs can be significantly reduced while preserving access to detailed, hive-level monitoring data across the entire apiary.

---

## Sensor Suite

The system was designed to collect a variety of measurements relevant to hive health, productivity, and security.

### Hive Weight Monitoring

Four 40 kg load cells are used to measure the total hive weight.

Applications:

- Nectar flow monitoring
- Honey production estimation
- Seasonal hive activity analysis

### Temperature Monitoring

A KTY81 temperature sensor measures internal hive temperature.

Applications:

- Colony health monitoring
- Detection of abnormal thermal conditions

### Humidity Monitoring

A DHT22 sensor measures humidity levels inside the hive environment.

Applications:

- Environmental monitoring
- Early detection of conditions affecting colony health

### Motion Detection

An ADXL335 accelerometer detects movement and vibration events.

Applications:

- Theft detection
- Unauthorized hive movement alerts
- Transport event monitoring

### Acoustic Monitoring

A microphone captures ambient and hive-related sounds.

Applications:

- Security monitoring
- Future analysis of colony activity patterns

### GPS Tracking

Integrated GPS functionality enables location tracking.

Applications:

- Hive recovery after theft
- Deployment tracking

---

## Hardware Design

The hardware platform was designed around an Arduino Uno-based architecture with dedicated interfaces for sensing, communication, data logging and power management.

### Schematic Overview

<img width="1214" height="869" alt="image" src="https://github.com/user-attachments/assets/81a8a645-664a-43c4-8865-fc3f22c6fa8a" />


High-level schematic of the master node showing the GSM, GPS, storage and sensor interfaces.

### PCB Layout

<img width="1306" height="533" alt="image" src="https://github.com/user-attachments/assets/8b55d9f5-def8-405f-8db9-2408a382bdd8" />


PCB layout of the master unit.

### 3D PCB Visualization

<img width="1546" height="677" alt="image" src="https://github.com/user-attachments/assets/4520eae8-1425-475b-a023-01e67953110b" />


3D rendering used to verify mechanical constraints and component placement.

## Communications

### Cellular Communication

Measured data is periodically transmitted to a central server through the mobile network using a SIM908 communication module.

### Local Data Logging

All relevant measurements can be stored locally on an SD card to prevent data loss during communication outages.

### RS-485 Network

The distributed architecture allows multiple slave units to communicate with a single master unit through an RS-485 bus.

Benefits:

- Long communication distances
- High noise immunity
- Scalable deployment
- Reduced communication hardware cost

---

## Power System

The complete system operates from a 12 V battery supply, allowing deployment in remote locations without grid power.

Design considerations included:

- Low power consumption
- Battery-powered operation
- Reliable field deployment
- Robust voltage regulation for sensitive electronics

---

## Engineering Responsibilities

My contribution focused exclusively on hardware engineering activities:

- Requirements analysis
- Electronic circuit design
- Schematic capture
- PCB layout design
- Interface design for all sensors
- Communication hardware design
- Power supply design
- Prototype manufacturing and assembly
- Hardware validation and testing

Software and backend development were outside the scope of my responsibilities.

---

## Design Challenges

Key engineering challenges included:

- Reliable operation in outdoor environments
- Integration of multiple sensor technologies
- Battery-powered operation
- RS-485 network implementation
- Cellular communication reliability
- Local data logging redundancy
- Theft detection and recovery functionality

---

## Project Results

The project successfully demonstrated a proof-of-concept smart beehive monitoring platform capable of:

- Remote hive monitoring
- Local and remote data collection
- Multi-node communication
- Security event detection
- GPS-based asset tracking

The hardware platform provided a foundation for scalable deployment in commercial and hobby beekeeping environments.

---

## Repository Contents

- System architecture diagrams
- Schematics
- PCB design screenshots
- Prototype photographs
- Hardware documentation
- Design notes

## Prototype

### Assembled Prototype

<img width="2253" height="1824" alt="IMG_20150219_130816~2" src="https://github.com/user-attachments/assets/5ffe41dd-58f6-4121-a0f2-5b8bae49584a" />
<img width="2295" height="1824" alt="IMG_20150219_192150~2" src="https://github.com/user-attachments/assets/169639d9-8cd0-4ad8-916e-1a1feeda91e0" />
<img width="2893" height="1327" alt="IMG_20150219_192224~2" src="https://github.com/user-attachments/assets/bbd298b4-ec3a-428e-af70-918d2cdf55c8" />
<img width="3200" height="1824" alt="IMG_20150219_192241" src="https://github.com/user-attachments/assets/7bcd6f8d-a889-486d-9bf2-ed113ae1b6ef" />





Prototype assembled and tested during development.
