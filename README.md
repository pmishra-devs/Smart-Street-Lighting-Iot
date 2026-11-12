💡 Smart Street Lighting System | IoT-Based Adaptive Lighting

An IoT-based Smart Street Lighting System developed using the ESP32-C3 Super Mini that automatically adjusts streetlight brightness according to ambient light conditions and vehicle movement.

The project combines LDR-based day/night detection, IR-based vehicle detection, adaptive brightness control, and a real-time Wi-Fi web dashboard to create an intelligent and energy-efficient street lighting solution.

🚀 Project Overview

Traditional street lighting systems often operate at full brightness throughout the night, leading to unnecessary energy consumption.

This project introduces an adaptive lighting solution that intelligently controls five streetlights based on environmental conditions and vehicle movement.

The system operates in three modes:

- Day Mode: All five streetlights remain OFF.
- Night Mode: All five streetlights operate at dim brightness to reduce unnecessary power consumption.
- Vehicle Detection Mode: When a vehicle is detected, the corresponding lighting zone automatically switches to full brightness and gradually returns to dim mode after the vehicle passes.

The ESP32-C3 also creates its own Wi-Fi network, allowing users to monitor the complete system through a web-based dashboard on a smartphone or computer.

✨ Key Features

- Automatic Day/Night Detection: Uses an LDR sensor to detect ambient light conditions.
- Adaptive Brightness Control: Automatically adjusts streetlight brightness according to vehicle movement.
- Vehicle Detection: Uses three IR sensors to detect vehicles in different zones.
- Zone-Based Lighting: Independently controls five streetlights using three IR sensor zones.
- Smooth Brightness Transition: Gradually increases and decreases brightness.
- IoT-Based Monitoring: Provides a live web dashboard through ESP32 Wi-Fi.
- Energy-Saving Estimation: Calculates estimated energy savings compared with continuous full-brightness operation.
- Standalone Wi-Fi Connectivity: Creates its own Wi-Fi access point without requiring an external router.
- Serial Monitoring: Displays real-time sensor readings and system status through the Arduino Serial Monitor.

🛠️ Hardware Components

Component| Quantity
ESP32-C3 Super Mini| 1
LDR Sensor| 1
10kΩ Resistor| 1
IR Obstacle Detection Sensors| 3
LED Streetlights| 5
Connecting Wires| As required
Power Supply| As required

⚙️ Working Principle

1. Day Mode ☀️

- The LDR detects sufficient ambient light.
- All five streetlights remain OFF.
- Vehicle detection does not activate the lights.

2. Night Mode 🌙

- The LDR detects darkness.
- All five streetlights turn ON at dim brightness.
- The default dim brightness is 40 out of 255.

3. Vehicle Detection Mode 🚗

When an IR sensor detects a vehicle, its corresponding lighting zone automatically increases to full brightness.

IR Sensor| Controlled Streetlights
IR1| L1 and L2
IR2| L3
IR3| L4 and L5

After vehicle detection stops, the corresponding streetlights remain at full brightness for 3 seconds before gradually returning to dim brightness.

🔌 Circuit Connections

ESP32-C3 Pin Configuration

Component| ESP32-C3 GPIO
LDR Analog Output| GPIO 0
IR Sensor 1| GPIO 1
IR Sensor 2| GPIO 3
IR Sensor 3| GPIO 4
Streetlight L1| GPIO 5
Streetlight L2| GPIO 6
Streetlight L3| GPIO 7
Streetlight L4| GPIO 10
Streetlight L5| GPIO 20

Hardware Note: Verify GPIO20 compatibility with your specific ESP32-C3 board, as it may be associated with USB D+. Use appropriate transistor/MOSFET driver circuits for controlling LED loads instead of connecting high-current lamps directly to ESP32 GPIO pins.

💻 Software Requirements

- Arduino IDE
- ESP32 Board Package
- C++ / Arduino Programming
- WiFi.h
- WebServer.h

Arduino IDE Configuration

1. Install the ESP32 board package.
2. Select ESP32C3 Dev Module.
3. Enable USB CDC On Boot.
4. Set Serial Monitor baud rate to 115200.
5. Upload the Arduino source code to the ESP32-C3.

📱 IoT Web Dashboard

The ESP32-C3 creates its own Wi-Fi access point for real-time system monitoring.

Wi-Fi Name: "SmartStreetLight"

Wi-Fi Password: "streetlight123"

Dashboard URL: "http://192.168.4.1"

Dashboard Monitoring

The web dashboard provides:

- Current DAY/NIGHT operating status.
- Live LDR sensor readings.
- Brightness percentage of all five streetlights.
- Vehicle detection status of all three IR sensors.
- Estimated energy savings percentage.

Dashboard Refresh Rate: 500 milliseconds.

🔧 Adjustable System Parameters

The following parameters can be modified directly in the Arduino source code.

Parameter| Default Value| Description
NIGHT_BELOW| 1200| Night detection threshold
DAY_ABOVE| 1600| Day detection threshold
DIM_LEVEL| 40| Default night brightness
FULL_LEVEL| 255| Maximum brightness
HOLD_MS| 3000 ms| Full-brightness hold duration
FADE_STEP| 5| Brightness transition step

⚡ Energy Efficiency

The system estimates energy savings by comparing the accumulated brightness values of the five streetlights against a theoretical full-brightness baseline.

By keeping streetlights dim when no vehicle is detected and increasing brightness only when necessary, the system aims to reduce unnecessary energy consumption.

Note: The displayed energy-saving percentage is a software-based brightness estimate, not a direct measurement of electricity consumption. Actual energy savings require electrical power measurement.

🧪 Testing and Project Status

Project Status: Hardware Prototype Tested

The project has been tested using the ESP32-C3-based hardware setup.

The implementation includes:

- LDR-based ambient light monitoring.
- IR-based vehicle detection.
- Five-lamp adaptive lighting control.
- Wi-Fi-based dashboard monitoring.
- Automatic brightness transitions.

🌍 Applications

- Smart City Infrastructure
- Intelligent Highway Lighting
- Residential Street Lighting
- Parking Areas
- College and University Campuses
- Automated Outdoor Lighting Systems

🔮 Future Improvements

- Cloud-based monitoring and data storage.
- Mobile application integration.
- Real-time electricity consumption measurement.
- Solar-powered streetlight integration.
- GPS-based vehicle tracking.
- Wireless communication between multiple streetlight units.
- Advanced traffic monitoring and intelligent lighting optimization.

📂 Project Structure

Smart-Street-Lighting-IoT/
│
├── README.md
├── LICENSE
└── Smart_Street_Lighting.ino

👨‍💻 Author

Pushkar Mishra

B.Tech – Robotics and Artificial Intelligence

Areas of Interest:

- Internet of Things (IoT)
- Embedded Systems
- Robotics and Automation
- Smart City Technologies

---

⭐ If you find this project interesting, consider giving this repository a star!

Building smarter, adaptive, and energy-efficient infrastructure through technology.