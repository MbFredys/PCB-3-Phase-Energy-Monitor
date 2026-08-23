# Three-Phase Energy Monitor

[![License: CERN-OHL-W-2.0](https://img.shields.io/badge/license-CERN--OHL--W%202.0-blue.svg)](https://ohwr.org/projects/cern-ohl/wikis/CERN-OHL-version-2)

Hardware design for a three-phase, four-wire energy-monitoring platform with Ethernet and Power over Ethernet, intended for future integration with building-management systems.

> **Project status:** Design and manufacturing documentation completed. The PCB has not been fabricated, calibrated, electrically validated, or tested for regulatory compliance.

## Project objective

The project explores an open and documented architecture capable of acquiring three-phase electrical measurements and exposing them through a connected embedded platform.

## System architecture

- **Measurement:** ATM90E32AS for 3P4W energy measurement
- **Controller:** ESP32-S3-MINI-1
- **Networking:** LAN8720A Ethernet PHY using RMII
- **Power:** TPS2378 PoE interface with local 5 V and 3.3 V rails
- **Sensing:** External current transformers and resistive voltage-sensing networks
- **Isolation:** Digital isolators between measurement and low-voltage digital domains
- **Development access:** USB and debugging/programming interfaces

## Engineering work

- Defined system requirements and functional architecture
- Selected the principal ICs, protection devices, connectors, and power components
- Developed the schematic and multi-domain PCB layout in KiCad
- Defined measurement, isolation, Ethernet, PoE, and power-distribution sections
- Prepared the BOM and manufacturing documentation

## Key design considerations

- Isolation boundaries and return-current paths
- Creepage and clearance around mains-related circuitry
- Mixed-signal grounding and decoupling
- Ethernet differential routing and PHY termination
- PoE power conversion and protection
- Calibration strategy for voltage and current channels

## Deliverables

The repository contains the available design source files and supporting manufacturing documentation. Review the repository structure before using any generated outputs.

## Validation still required

A physical prototype is required to verify:

- Electrical safety and isolation distances
- Measurement accuracy and calibration
- Ethernet and PoE operation
- Thermal behavior and power integrity
- EMC/EMI performance
- Compliance with any applicable product or installation standards

This repository should be treated as an engineering design project, not as a certified or production-ready energy meter.

## License

Licensed under CERN-OHL-W-2.0.
