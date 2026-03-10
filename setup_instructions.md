# Setup Instructions

This guide explains how to set up and run the Smart IoT Medication Scheduling and Reminder System locally.

The system consists of three main components:
1. Backend Server (Node.js)
2. Web Dashboard (HTML, CSS, JavaScript)
3. ESP32 IoT Device Firmware

Follow the steps below to run the complete system.

------------------------------------------------------------

1. Clone the Repository

Open a terminal and run:

git clone https://github.com/yourusername/smart-medicine-reminder.git
cd smart-medicine-reminder

------------------------------------------------------------

2. Backend Setup (Node.js Server)

Install Node.js (version 18 or higher):

https://nodejs.org/

Verify installation:

node -v
npm -v

------------------------------------------------------------

Install Backend Dependencies

Navigate to the backend folder:

cd backend

Install required packages:

npm install

------------------------------------------------------------

Configure Environment Variables

Create a .env file inside the backend directory and add the following:

PORT=5000
MONGODB_URI=mongodb://localhost:27017/medicine_reminder
JWT_SECRET=your_secret_key
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password

------------------------------------------------------------

Start the Backend Server

Run the backend server using:

npm start

or

node server.js

If successful, the server will start on:

http://localhost:5000

------------------------------------------------------------

3. MongoDB Setup

Install MongoDB Community Edition:

https://www.mongodb.com/try/download/community

Start the MongoDB service.

Verify installation using:

mongosh

Create the database:

medicine_reminder

The backend will automatically create required collections when the server runs.

------------------------------------------------------------

4. Frontend Setup (Web Dashboard)

Navigate to the frontend folder:

cd ../frontend

Since the frontend uses HTML5, CSS3, and JavaScript, no installation is required.

Simply open the dashboard by opening the following file in a browser:

index.html

Alternatively, you can run a simple local server:

npx serve .

Then open:

http://localhost:3000

------------------------------------------------------------

5. ESP32 Firmware Setup

Install Arduino IDE:

https://www.arduino.cc/en/software

------------------------------------------------------------

Install ESP32 Board Support

1. Open Arduino IDE
2. Go to File → Preferences
3. Add the following URL in "Additional Board Manager URLs":

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

4. Open Boards Manager
5. Install "ESP32 by Espressif Systems"

------------------------------------------------------------

Install Required Arduino Libraries

Open Arduino IDE → Library Manager and install:

WiFi
HTTPClient
ArduinoJson
RTClib
LiquidCrystal_I2C
Adafruit PWM Servo Driver
HX711

------------------------------------------------------------

Upload ESP32 Firmware

Open the firmware file:

hardware/esp32_code.ino

Update the WiFi credentials inside the code:

#define WIFI_SSID "your_wifi_name"
#define WIFI_PASSWORD "your_wifi_password"

Connect the ESP32 using USB.

Select board:

ESP32 Dev Module

Then click Upload.

------------------------------------------------------------

6. Hardware Connections

Main hardware components used in the system:

ESP32 Development Board  
DS3231 RTC Module  
PCA9685 Servo Driver  
SG90 Servo Motors (3 compartments)  
HC-SR04 Ultrasonic Sensors  
Load Cells with HX711 Amplifier  
Buzzer  
LED Indicators  
16x2 LCD Display with I2C Module  

Ensure all modules share a common ground and proper voltage levels:
5V supply for actuators and 3.3V logic for ESP32 and sensors.

------------------------------------------------------------

7. Running the Full System

1. Start MongoDB
2. Start the backend server
3. Open the web dashboard in a browser
4. Power the ESP32 device
5. Configure medication schedules from the dashboard

The ESP32 will automatically synchronize schedules with the backend and log medication events.

------------------------------------------------------------

8. Troubleshooting

ESP32 not connecting to WiFi
- Verify WiFi credentials
- Ensure the network is 2.4 GHz

Backend cannot connect to MongoDB
- Ensure MongoDB service is running
- Verify MONGODB_URI in the .env file

Dashboard not displaying data
- Ensure backend server is running
- Verify API URL used in frontend JavaScript

------------------------------------------------------------

9. Notes

This project was developed as part of an academic research project focused on improving medication adherence using IoT-based monitoring systems.