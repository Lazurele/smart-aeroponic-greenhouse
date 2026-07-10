# Smart Vertical Aeroponic Greenhouse System

An automated, IoT-based environmental control and remote monitoring system designed for vertical aeroponic farming. This project features a dual-controller architecture that optimizes plant growth conditions while maximizing space and water efficiency.

🏆 **Awarded:** Best Student Researcher

---

## 🚀 Features

* **Dual-Controller Automation:** Efficient workload separation using a Master-Slave system configuration.
* **Vertical Aeroponics:** Space-saving agricultural design utilizing suspended root systems for faster growth and less water usage than traditional soil farming.
* **IoT Remote Monitoring:** A dedicated cloud-connected dashboard to monitor system health and sensor telemetry from anywhere.
* **Real-Time Responsiveness:** Dedicated hardware handling ensures instant actuation based on changing environmental parameters.

---

## 📊 System Architecture & Communication

The system utilizes a dual-controller, **Master-Slave architecture** to split high-level computing and network tasks from real-time hardware execution:

1. **Raspberry Pi (The Brain):** Acts as the master controller. It processes incoming telemetry, handles high-level automation logic, runs edge processing, and manages IoT cloud connectivity for remote monitoring.
2. **Arduino Mega (The Handler):** Acts as the slave controller. It directly interfaces with the physical sensor array and actuators, handling time-sensitive hardware tasks.

### Data & Command Flow:
* **Sensor Telemetry:** Arduino Mega reads raw data from sensors $\rightarrow$ Sends data packets to the Raspberry Pi via Serial communication.
* **IoT Uplink:** Raspberry Pi parses and processes the data $\rightarrow$ Pushes live telemetry to the cloud dashboard via IoT protocols.
* **Automation Control:** Raspberry Pi analyzes the data against pre-set parameters $\rightarrow$ Sends command strings back to the Arduino Mega $\rightarrow$ Arduino Mega instantly switches the appropriate relays/actuators.

## 🛠️ Hardware & Components

* **Processors & Microcontrollers:** 
  * Raspberry Pi 5 / 4 (Master Node)
  * Arduino Mega 2560 (Slave Node)
* **Sensors:** 
  * DHT11 / DHT22 (Ambient Temperature & Humidity)
  * pH Sensor & EC (TDS) Sensor (Nutrient Solution Quality)
  * Water Level Sensor (Reservoir Monitoring)
* **Actuators & Modules:**
  * High-Pressure Water Pump (For aeroponic misting)
  * Fans (Humidity Control)
  * Motors (Aeropnic Tower Rotation)
  * 5V / 12V Relay Modules
  * Grow Lights (LED Spectrum)

---

## 💻 Software & Protocols

* **Firmware:** C++ (Arduino IDE) for hardware handling.
* **Edge Scripts:** Python (Running on Raspberry Pi OS).
* **Communication:** Serial (UART over USB) between controllers.
* **IoT Protocol:** [e.g., MQTT / HTTP REST API / WebSockets]
* **Cloud Dashboard:** [e.g., Blynk / ThingsBoard / Node-RED / Firebase]

---

## ⚙️ How It Works (Step-by-Step)

1. **Data Acquisition:** The Arduino Mega continuously polls the ambient sensors (temperature, humidity) and reservoir metrics (pH, tds and water levels).
2. **Serial Communication:** The Mega packets this data and transmits it to the Raspberry Pi over a serial link.
3. **High-Level Logic & IoT Sync:** The Raspberry Pi parses the data, updates the remote IoT monitoring dashboard, and evaluates the environment against the user-defined agricultural parameters.
4. **Actuation:** If a parameter is breached (e.g., temperature is too high), the Pi sends a specific command string down to the Arduino Mega, which instantly triggers the corresponding relay to activate the cooling mechanism.

---

## 📸 Visuals

| System Overview | Circuit & Wiring | IoT Dashboard |
|---|---|---|
| [imgDocumentary/Schematic Flow Chart.jpg] | *[Insert a photo of your PCB or breadboard wiring]* | *[Insert a screenshot of your phone/web dashboard]* |

*(Note: To display your actual photos here on GitHub, upload the images to your repository folder and replace the text inside the brackets with your image paths, e.g., `img/greenhouse.jpg`)*

---

## 👤 Author

* **Engr. L A Jhon A. Tilla-in, ECT**
* Email: l.tillain.ece@gmail.com
* LinkedIn: [Your LinkedIn Link]
