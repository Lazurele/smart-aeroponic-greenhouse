# Smart Vertical Aeroponic Greenhouse System

An automated, IoT-based environmental control and remote monitoring system designed for vertical aeroponic farming. This project features a dual-controller architecture that optimizes plant growth conditions while maximizing space and water efficiency.

🏆 **Awarded:** Best Student Researcher

---

## 🚀 Features

* **Dual-Controller Automation:** Efficient workload separation using a Master-Slave system configuration.
* **Vertical Aeroponics:** Space-saving agricultural design utilizing suspended root systems for faster growth and 90%+ less water usage than traditional soil farming.
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
