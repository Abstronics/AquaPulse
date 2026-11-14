# AquaPulse 💧
### Smart Water Monitoring and Pump Management System

AquaPulse is an IoT-based water monitoring and pump management system designed to improve water availability in hostels. It monitors overhead tank water levels, estimates water consumption, and automates pump operations.

The system provides a web-based dashboard where supervisors can monitor water availability and control the pumping machine. It also features a physical start/stop button for local pump operation and a buzzer for audible fault indication.

## 🎯 Problem Statement

Water unavailability is a recurring challenge in many hostels. Students may experience water shortages because tank levels are not monitored consistently or pumping machines are not activated when needed.

AquaPulse addresses this problem by introducing intelligent water-level monitoring and automated pump management, helping supervisors maintain better control over water availability.

## 🚀 Key Features

- **Real-Time Water Level Monitoring:** Monitors the overhead tank using an ultrasonic sensor.
- **Automatic Pump Control:** Automatically starts and stops the pump based on configurable water-level thresholds.
- **Local Pump Control:** Allows the supervisor to start or stop the pump using a physical push button.
- **Web-Based Pump Control:** Provides pump ON/OFF control through the supervisor dashboard.
- **Water Consumption Estimation:** Estimates water consumption by analysing changes in the overhead tank level.
- **Water Availability Monitoring:** Displays current water level and availability status.
- **Water Shortage Prediction:** Estimates how long the remaining water may last using recent consumption patterns.
- **Fault Detection:** Identifies sensor failures, abnormal water-level changes, and suspected pump faults.
- **Local Fault Indication:** Uses an active buzzer to provide audible alerts for critical conditions.
- **Pumping History:** Records pump activation events and operating durations.

## 🛠️ Hardware Components

| Component | Quantity | Purpose |
|---|---:|---|
| ESP32 Development Board | 1 | Main system controller |
| Waterproof Ultrasonic Sensor | 1 | Monitors overhead tank water level |
| Relay Module | 1 | Controls pump switching |
| Physical Push Button | 1 | Local pump start/stop control |
| Active Buzzer | 1 | Audible fault indication |
| Regulated Power Supply | 1 | Powers the control electronics |


## ⚙️ System Architecture

AquaPulse uses an ESP32 as its central controller.

1. The ultrasonic sensor measures the water level in the overhead tank.
2. The ESP32 processes the readings and calculates the tank's water level and availability.
3. The controller automatically starts the pump when the water level reaches the configured low threshold.
4. Pumping stops when the tank reaches its configured upper threshold.
5. A physical push button allows local starting and stopping of the pump.
6. The supervisor can also control the pump through the web dashboard.
7. The system monitors operating conditions and activates the buzzer when critical faults are detected.

## 🔄 Pump Control Logic

AquaPulse supports automatic and manual pump operation.

**Automatic Mode**
- Pump starts when the overhead tank reaches the configured low-water threshold.
- Pump stops when the overhead tank reaches the configured high-water threshold.
- Safety conditions take priority over normal pump operation.

**Manual Mode**
- The supervisor can start or stop the pump through the dashboard.
- The physical push button can also toggle the pump ON or OFF locally.

The physical stop command must take priority over automatic and dashboard commands. Safety interlocks must remain active in every operating mode.

## 💻 Software and Technologies

- **Embedded Programming:** Arduino C/C++
- **Microcontroller:** ESP32
- **Wireless Communication:** Wi-Fi
- **Web Interface:** HTML, CSS and JavaScript
- **Web Server:** ESP32 WebServer
- **Sensor Processing:** Ultrasonic distance measurement and tank-level calculations
- **Data Processing:** Water consumption estimation and water availability analysis
  

## 📊 Supervisor Dashboard

AquaPulse provides a dedicated supervisor dashboard with:

- Live overhead tank water level.
- Water availability percentage.
- Estimated remaining water.
- Estimated water consumption.
- Pump ON/OFF status.
- Automatic/manual operating mode.
- Remote pump ON/OFF controls.
- Fault notifications.
- Pumping history and operating duration.

The dashboard is designed exclusively for authorised supervisor access.

## 🔔 Fault Detection and Safety

The system is designed to identify important operating conditions, including:

- Pump operating without a corresponding increase in tank level.
- Abnormal water-level reduction.
- Excessive pump operating duration.


The physical pump stop control must remain effective even when Wi-Fi connectivity is unavailable. Appropriate electrical protection must also be provided to protect the pump and control system.

## 📐 Water Consumption Estimation

AquaPulse estimates water consumption by monitoring changes in the overhead tank's water level.

Using the calibrated tank dimensions, changes in water height can be converted into estimated changes in water volume.


## 📌 Project Status

**Development in Progress**

AquaPulse is being developed as an embedded IoT water management solution combining sensor-based monitoring, automated pump control, local operation, and web-based supervision.

## 🎯 Project Goal

To improve water availability in hostels through intelligent water monitoring, automated pump management, and accessible control for supervisors.

---

**AquaPulse — Smarter Water Monitoring. Better Water Availability.**
