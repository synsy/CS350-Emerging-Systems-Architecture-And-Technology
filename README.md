# Raspberry Pi Temperature & Thermostat Projects

This repository contains two Python projects developed for embedded systems coursework using a Raspberry Pi. Both projects demonstrate the integration of hardware components (temperature sensors, LEDs, buttons, and a 16x2 LCD) with software-driven **state machines** to control outputs and manage user interaction.

---

## 📑 Table of Contents
- [Overview](#overview)  
- [Requirements](#requirements)  
- [Running the Programs](#running-the-programs)  
- [Reflection](#reflection)  
- [Next Steps](#next-steps)

---

## Overview

### Temperature Sensor Integration (`TemperatureSensorIntegration.py`)
- Reads temperature/humidity from an **AHTx0 sensor**.  
- Displays data on a **16x2 LCD**.  
- Button toggles between Celsius/Fahrenheit.  
- State machine manages the scale.  

### Thermostat (`Thermostat.py`)
- Three states: **Off**, **Heat**, **Cool**.  
- LEDs: Red = Heat, Blue = Cool (pulse/solid depending on setpoint vs temp).  
- Buttons: cycle states, adjust setpoint (±1°F).  
- LCD alternates between **time/temp** and **state/setpoint**.  
- Sends **serial update** every 30s with state, temp, and setpoint.  

---

## Requirements
- **Hardware:** Raspberry Pi, AHTx0 sensor (I²C), 16x2 LCD, LEDs + resistors, Buttons.  
- **Libraries:** `gpiozero`, `statemachine`, `adafruit-circuitpython-ahtx0`, `adafruit-circuitpython-charlcd`, `pyserial`.  

Install:
```bash
pip install gpiozero python-statemachine adafruit-circuitpython-ahtx0 adafruit-circuitpython-charlcd pyserial
```

---

## Running the Programs

**Temperature Sensor Integration**
```bash
python TemperatureSensorIntegration.py
```

**Thermostat**
```bash
python Thermostat.py
```

---

## Reflection

- **Summary:** Built two Raspberry Pi projects integrating sensors, LEDs, and LCDs with state machines.  
- **Strengths:** Clear state machine design, modular LCD handling, correct LED/serial behavior.  
- **Improvements:** Add error handling, button debounce, and testing.  
- **Resources:** Adafruit libraries, Raspberry Pi GPIO docs, `statemachine` library.  
- **Transferable Skills:** State machines, hardware integration, threading, modular design.  
- **Maintainability:** Modular classes, comments, DEBUG flags, event-driven programming.  

---

## Next Steps
- Add error handling and logging.  
- Add testing for state transitions.  
- Expand thermostat with networking/cloud monitoring.  
