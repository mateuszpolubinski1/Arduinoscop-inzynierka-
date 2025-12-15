# ArduinoScope – Modular Educational Measurement Device
*A universal, low-cost measurement platform based on Raspberry Pi Pico*

![19797808-9ae3-465f-a71c-d99da3b4bd1f](https://github.com/user-attachments/assets/3c638cda-dc53-4ad2-8e2a-278a4d2c2577)


---

## Overview
ArduinoScope is a **modular electronic measurement device** designed as an educational platform for electronics and metrology laboratories.  
The project was developed as an **engineering thesis** and combines **analog front-end design**, **ADC-based signal acquisition**, and **embedded software development**.

The device is built around the **Raspberry Pi Pico (RP2040)** microcontroller and can be reconfigured via software to operate as:
- Oscilloscope
- Spectrum analyzer
- Wobuloscope
- Vector voltmeter
- Frequency counter

---

## System Architecture
The system is based on a **modular architecture**, consisting of a mainboard and multiple plug-in expansion modules.

<img width="1932" height="1507" alt="image" src="https://github.com/user-attachments/assets/133728ef-fb6d-4f42-8dfa-2eda6af6f718" />


Key blocks of the system:
- Modular analog input boards
- Mainboard with Raspberry Pi Pico (RP2040)
- Internal ADC for signal acquisition
- TFT display with touchscreen
- USB interface for communication with a PC
- Dedicated power supply module

---

## Analog Front-End Design
Two independent analog input paths were designed to support different measurement scenarios.

### Differential Input Path
<img width="692" height="469" alt="image" src="https://github.com/user-attachments/assets/5f8b5849-c3c0-4531-a2b8-bc4ee0750ac8" />


- Based on **INA2137 instrumentation amplifier**
- Fixed gain using precision, internally matched resistors
- High common-mode rejection (CMRR)
- Enables voltage measurement between any two points in a circuit
- Dedicated overvoltage protection to protect the ADC

---

### Single-Ended Input Path
<img width="729" height="477" alt="image" src="https://github.com/user-attachments/assets/ad8afac8-4c91-41ce-8992-ae72d7bbaab9" />


- Based on **OPA1644 / TL084 operational amplifiers**
- Electronically adjustable gain
- Separate signal paths for DC and AC components
- Software-controlled signal conditioning similar to a classic oscilloscope
- Input and output protection for safe educational use

---

## Protection & Signal Conditioning
To ensure robustness and safe operation:
- Input protection using **BAV99-AQ diodes** (low leakage, low capacitance)
- ADC protection using **BAS40 Schottky diodes**
- Precision voltage references (**TL431**, **LM385**) for proper ADC range adaptation
- Designed to withstand accidental overvoltage conditions during laboratory exercises

---

## PCB Design
Custom printed circuit boards were designed using **KiCad**, with particular attention to analog signal integrity.

<img width="1936" height="854" alt="image" src="https://github.com/user-attachments/assets/b00b64c9-269d-4aaa-853f-54af32990313" />
<img width="1681" height="795" alt="image" src="https://github.com/user-attachments/assets/917e65bb-128d-4a55-89b6-048ccf4fe22e" />
<img width="1681" height="795" alt="image" src="https://github.com/user-attachments/assets/5fa32654-d9b7-48c2-b9ff-0caf878b1083" />
<img width="1724" height="791" alt="image" src="https://github.com/user-attachments/assets/b4db2c8a-d295-47c3-813b-ef5ea9bfe425" />
<img width="1622" height="794" alt="image" src="https://github.com/user-attachments/assets/6fd2164d-1e2b-4d8b-b023-3b8fa9c67945" />





PCB design highlights:
- Modular plug-in boards connected via pin headers
- Noise-aware routing and ground plane usage
- Separation of analog and digital sections
- Easy manufacturing and repair

---

## Software
The firmware was developed using:
- **Arduino**
- **MicroPython**

Main software features:
- Data acquisition from internal ADC
- Signal processing and scaling
- User interface handling (display and touchscreen)
- USB communication for offline data transfer to PC

---

## Measurements & Validation
The device was validated through laboratory measurements.

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/6dbe5b55-48be-47fe-afe8-dc940301246f" />
<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/7937b451-c087-4aeb-b4f6-35a70435afee" />


Validation results:
- Correct operation within the acoustic frequency range
- Stable gain and offset control
- Proper operation of protection circuits
- Reliable signal acquisition using the RP2040 ADC

---

## User Interface
The built-in TFT display provides direct visualization of measured signals.

The user interface allows real-time interaction and configuration without the need for an external computer.

---

## Technologies Used
**Hardware**
- Raspberry Pi Pico (RP2040)
- INA2137, OPA1644, TL084
- AD9850 signal generator
- PCF8575 I/O expander

**Software & Tools**
- Arduino, MicroPython
- KiCad, LTspice
- Oscilloscope and laboratory measurement equipment

---

## Project Status & Future Work
Status:
- Fully functional prototype
- Successfully tested in laboratory conditions

Possible future improvements:
- External higher-resolution ADC
- Improved bandwidth and noise performance
- PC-based visualization and analysis software

---

## Author
**Mateusz Połubiński**  
Electronics Engineering – Warsaw University of Technology

