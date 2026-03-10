# Smart IoT Medication Scheduling and Reminder System

## Overview
Medication adherence is a major challenge, particularly for elderly patients and individuals managing chronic conditions. Missing scheduled doses can lead to serious health complications and reduced treatment effectiveness.

This project presents an **IoT‑based Smart Medication Scheduling and Reminder System** that not only reminds patients to take medication but also verifies whether the dose was actually taken. The system integrates embedded hardware with a web‑based monitoring platform, enabling caregivers to remotely manage medication schedules and track adherence.

The device is built around an **ESP32 microcontroller** connected to sensors and actuators, while a **Node.js backend and MongoDB database** handle scheduling, logging, and communication with a web dashboard.

---

## System Architecture

The system consists of three main layers:

1. **IoT Device Layer**
   - ESP32 microcontroller
   - DS3231 RTC module for accurate scheduling
   - Servo‑controlled compartments for medication access
   - Ultrasonic sensors for user interaction detection
   - LED indicators and buzzer for alerts

2. **Backend Layer**
   - Node.js server
   - MongoDB database
   - REST API for device communication and data logging

3. **Web Dashboard**
   - Built using **HTML5, CSS3, and JavaScript**
   - Allows caregivers to configure medication schedules
   - Displays adherence history and device status

---

## Key Features

- Scheduled medication reminders using RTC
- Ultrasonic sensor based user interaction detection
- Servo controlled medication compartments
- Web based caregiver dashboard
- Role‑based access control
- Remote medication scheduling
- Adherence history logging
- Device online/offline monitoring
- Support for managing multiple patients from one caregiver account

---

## Hardware Components

- ESP32 Development Board (38‑pin CP2102)
- DS3231 RTC Module
- PCA9685 16‑Channel PWM Servo Driver
- SG90 Servo Motors (3)
- HC‑SR04 Ultrasonic Sensors (3)
- Buzzer
- RGB LEDs
- 16x2 LCD Display with I2C Module
- Jumper wires and power supply

---

## Software Stack

### Frontend
- HTML5
- CSS3
- JavaScript

### Backend
- Node.js
- Express.js

### Database
- MongoDB

### Embedded Programming
- Arduino Framework for ESP32

---

## How the System Works

1. A caregiver logs into the web dashboard and sets medication schedules.
2. The backend stores the schedule in the database.
3. The ESP32 periodically fetches the schedule from the server.
4. At the scheduled time:
   - LED and buzzer alerts are activated.
   - Ultrasonic sensor detects if a user approaches the device.
5. If a user is detected:
   - The corresponding compartment opens using a servo motor.
   - The system logs the dose as **taken**.
6. If no interaction:
   - The dose is logged as **missed**.
7. Caregivers can view medication history through the dashboard.

---

## Repository Structure

ASAC_Capstone_2026_IoT_Based_Medicine_Reminder_System/
│
├── src/
│   │
│   ├── backend/
│   │   │
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   └── role.js
│   │   │
│   │   ├── models/
│   │   │   ├── DoseLog.js
│   │   │   ├── DoseTime.js
│   │   │   ├── Patient.js
│   │   │   └── User.js
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── device.js
│   │   │   ├── doseLog.js
│   │   │   ├── doseTime.js
│   │   │   └── patient.js
│   │   │
│   │   ├── package-lock.json
│   │   ├── package.json
│   │   └── server.js
│   │
│   ├── ESP32/
│   │   └── SmartMed.ino
│   │
│   └── frontend/
│       │
│       ├── assets/
│       │   └── images/
│       │
│       ├── auth.js
│       ├── device.js
│       ├── patient.js
│       ├── script.js
│       ├── login.js
│       ├── signup.js
│       │
│       ├── index.html
│       ├── login.html
│       ├── signup.html
│       │
│       └── style.css
│
├── architecture.png
├── demo_video_link.txt
├── README.md
├── requirements.txt
└── setup_instructions.md

---

## Applications

- Elderly patient medication management
- Chronic disease treatment monitoring
- Remote caregiver supervision
- Assisted living environments

---

## Future Improvements

- Mobile application integration
- AI‑based medication adherence prediction
- Advanced health monitoring sensors
- Offline data synchronization for low‑connectivity environments
- Biometric authentication for secure access

---

## Authors

Roshan Chourasia  
Nishanth B K  
Farhan Hyder N  
Rachana Venkatachalapathy  

Department of Computer Science and Engineering  
Alliance University, Bengaluru, India

---

## License

This project is developed for academic and research purposes.

