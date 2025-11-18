# ⚡Energy-Monitoring-PCB
A high-accuracy, isolated and PoE-powered three-phase energy monitoring system, designed for integration with Building Management Systems (BMS) in office, commercial, and industrial environments.

🌍 Overview
This PCB is a 3-phase 4-wire (3P4W) electrical monitoring module designed to be installed at the main power entry of an office or small facility.
It measures all critical electrical parameters in real time and transmits them via Ethernet to an external BMS, which handles control and decision-making.

# 🎯 Problem This Project Solves
Most commercial power meters are:
1. Expensive
2. Closed and hard to integrate
3. Limited in data access
4. Not based on modern precision chips
5. Lacking PoE connectivity
6. Not open-hardware or customizable

This design solves those issues by providing an open, reproducible, integrable, and fully documented energy-monitoring board.

# 🚀 Main Features
🔌 Professional Energy Measurement (ATM90E32AS)
1. Full 3-phase 4-wire (3P4W) measurement 
2. Internal computation of:
  - RMS voltage
  - RMS current
  - Active, reactive, and apparent power
  - Power factor
  - Frequency
  - Per-phase energy accumulation
3. High-precision resistive voltage dividers
4. Current sensing via external CTs
5. Full isolation between mains and low-voltage electronics

# 🌐 Ethernet + PoE Connectivity
1. LAN8720A Ethernet PHY with proper terminations / EMI practices
2. 10/100 Mbps stable Ethernet link
3. PoE 802.3af powered through TPS2378DDAR
4. Surge, ESD, and transient protection on all Ethernet lines

# 🧠 ESP32-S3-MINI-1 Controller
1. SPI communication with the energy IC through digital isolators (Si86xx)
2. Native USB for programming
3. JTAG for debuging
4. Processes measurements and publishes data to the BMS
5. Supports OTA updates

# 🔋 Robust Power Architecture
1. PoE → 5V → 3.3V conversion using MAX17521ATG
2. Fully isolated DC domain for the measurement section
3. MOVs, TVS diodes, PTC fuses, and proper filtering throughout the design

# 🛡️ Safety & Isolation
Clear separation between:
  - High-voltage domain (AC mains)
  - Low-voltage domain (ESP32, PHY, logic)
  - Creepage/clearance compliant with IEC standards
  - Multi-stage protection for safe installation in real electrical panels

# 🆚 Why This Design Is Better Than Similar Products
1. Fully documented, open-hardware
2. Native PoE, uncommon in industrial meters
3. Based on the highly accurate ATM90E32AS chip
4. Correct Ethernet PHY terminations: Bob Smith, CT biasing, TVS, filters
5. Fully isolated architecture for industrial safety
6. Cheaper and more flexible than commercial closed energy analyzers
7. Designed for reproducibility, manufacturing, and long-term reliability

# 🛠️ Usage
1. Connect the PCB to the incoming three-phase line (3 phases + neutral).
2. Attach CTs to each phase.
3. Power the board using a PoE switch.
4. Connect to Ethernet and pair with the BMS.
5. Firmware reads and transmits all electrical parameters.

# 🚀 Getting Started
1. Clone this repository
2. Open the design files in KiCad
3. Review critical areas:
  - Isolation boundaries
  - Voltage dividers
  - Differential Ethernet routing
  - PoE and DC-DC power chain
4. Manufacture the PCB (PCBWay / JLCPCB recommended)
5. Assembly order:
  - Power stage
  - PoE stage
  - Isolators
  - ESP32-S3
  - Connectors and passives
6. Program the ESP32-S3 via USB
7. Install and verify measurements

# License
This project is licensed under the MIT License. See the [MIT License ↗](https://opensource.org/license/mit/) file for more information.
🪪 License

This project is licensed under the MIT License.
