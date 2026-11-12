💡 Smart Street Lighting System | IoT-Based Adaptive Lighting

An intelligent IoT-based street lighting system built using the ESP32-C3 Super Mini that automatically adjusts streetlight brightness according to ambient light conditions and vehicle movement.

The system uses an LDR sensor to detect day and night conditions and three IR sensors to detect vehicles. It provides adaptive lighting, energy-efficient operation, and real-time monitoring through a Wi-Fi-based web dashboard.

🚀 Project Overview

Traditional streetlights generally remain ON at full brightness throughout the night, resulting in unnecessary energy consumption.

This project introduces an intelligent lighting solution that automatically controls streetlight brightness based on environmental conditions and vehicle movement.

During daytime, all lights remain OFF. At night, all lights operate at dim brightness. When a vehicle is detected, the corresponding streetlight zone automatically increases to full brightness and gradually returns to dim mode after the vehicle passes.

✨ Key Features

- Automatic Day/Night Detection: Uses an LDR sensor to detect ambient light.
- Adaptive Brightness Control: Adjusts brightness according to vehicle movement.
- Vehicle Detection: Uses three IR sensors to detect vehicles in different zones.
- Zone-Based Lighting: Controls five streetlights through three independent zones.
- Smooth Brightness Transition: Implements gradual fading between brightness levels.
- IoT Monitoring: Provides a real-time web dashboard through ESP32 Wi-Fi.
- Energy Monitoring: Estimates energy savings compared with continuously operating all lamps at full brightness.
- Standalone Operation: Creates its own Wi-Fi access point without requiring an external router.

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

The system operates in three main conditions:

1. Day Mode ☀️

- LDR detects sufficient ambient light.
- All five streetlights remain OFF.
- Vehicle detection does not activate the lights.

2. Night Mode 🌙

- LDR detects darkness.
- All five streetlights turn ON at dim brightness.
- This reduces unnecessary power consumption.

3. Vehicle Detection Mode 🚗

When an IR sensor detects a vehicle, its corresponding lighting zone switches to full brightness.

IR Sensor| Controlled Streetlights
IR1| L1 and L2
IR2| L3
IR3| L4 and L5

After the vehicle passes, the corresponding lights remain bright for a predefined duration and then gradually return to dim brightness.

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

Note: Verify GPIO20 compatibility with your particular ESP32-C3 board, as it may be used for USB connectivity. Use suitable transistor/MOSFET driver circuits for lamps instead of connecting high-current loads directly to ESP32 GPIO pins.

💻 Software Requirements

- Arduino IDE
- ESP32 Board Package
- C++ / Arduino Programming
- Wi-Fi Library
- WebServer Library

Arduino IDE Configuration

1. Install the ESP32 board package.
2. Select ESP32C3 Dev Module.
3. Enable USB CDC On Boot.
4. Set Serial Monitor baud rate to 115200.
5. Upload the program to the ESP32-C3.

📱 IoT Web Dashboard

The ESP32 creates its own Wi-Fi access point.

Wi-Fi Name: "SmartStreetLight"

Password: "streetlight123"

Dashboard URL: "http://192.168.4.1"

The dashboard displays:

- Current DAY/NIGHT status
- Live LDR sensor readings
- Brightness percentage of all five streetlights
- Vehicle detection status of all three IR sensors
- Estimated energy savings percentage

Dashboard data refreshes every 500 milliseconds.

🔧 Adjustable Parameters

The following parameters can be modified in the Arduino code:

Parameter| Default Value| Purpose
NIGHT_BELOW| 1200| Night detection threshold
DAY_ABOVE| 1600| Day detection threshold
DIM_LEVEL| 40| Night brightness
FULL_LEVEL| 255| Maximum brightness
HOLD_MS| 3000 ms| Full-brightness hold time
FADE_STEP| 5| Brightness transition speed

⚡ Energy Efficiency

The system estimates energy savings by comparing accumulated lamp brightness against the theoretical brightness of all five lamps operating continuously at full brightness during nighttime.

Actual energy savings depend on lamp power, operating duration, and vehicle movement.

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

📌 Project Status

Development: Working prototype / Testing and Calibration.

👨‍💻 Author

Pushkar Mishra

B.Tech – Robotics and Artificial Intelligence

Interested in IoT, Embedded Systems, Automation, and Smart City Technologies.

---

⭐ If you find this project interesting, feel free to explore the source code and contribute to its improvement.

Building smarter and more energy-efficient infrastructure through technology!
