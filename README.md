# Fault Detection and Analysis System for Transmission lines

This project focuses on **detecting, classifying, and approximately locating faults** occurring in **three-phase transmission lines** using an **ESP32 microcontroller** and **CT sensors**.  
It was developed as part of my **Final Year Project** in Electrical Engineering.

## Objective
To design a real-time fault detection and classification system for transmission lines that can:
  - Detect **Line-to-Line**, **Line-to-Ground**, **Overload**, and **Overvoltage** faults.
  - Classify the type of fault accurately.
  - Estimate the **approximate fault location** along the line.
  - Provide rapid fault information to improve reliability and minimize downtime.

### Working Principle
1. **Power Supply:**
   - Three lithium-ion batteries (combined ≈ 6.5V) supply power to the ESP32 microcontroller.
2. **3-Phase Supply Generation:**
   - A **BLDC motor** with a speed controller generates the 3-phase AC supply.
3. **Measurement & Monitoring:**
   - **CT Sensor (ZMCT103)** measures line current.
   - One terminal connects to the transmission line; the other connects to the ESP32 via a voltage divider.
4. **Fault Simulation:**
   - The line is modeled with **three towers spaced 150m apart**, each segment having a **1.5Ω resistance**.
5. **Fault Detection Logic:**
   - The ESP32 continuously monitors current and voltage.
   - When a variation exceeds predefined thresholds, the system identifies:
     - **Fault Type** → Line-to-Line, Line-to-Ground, Overload and Overvoltage.  
     - **Approximate Location** → Based on impedance and voltage drop analysis

## Key Highlights
1. Real-time fault detection and classification  
2. Impedance-based location estimation  
3. Low-cost implementation using ESP32 and CT sensors  
4. Supports multiple fault types (L–L, L–G, Overload, Overvoltage)  
5. Modular design for future IoT integration  

## Components Used
| **Component** | **Description** |
|------------|-------------|
| **ESP32** | Main microcontroller for processing |
| **BLDC Motor + Controller** | Generates 3-phase AC |
| **CT Sensor (ZMCT103)** | Measures current in each phase |
| **Lithium-ion Batteries (x3)** | Power supply (≈6.5V total) |
| **Voltage Divider Circuit** | Scales voltage for ESP32 input |
| **Resistors (1.5Ω each)** | Line segment simulation |
| **Transmission Line Model** | 3 towers, 150m apart each |

## Results
- Successfully detected and classified various fault types.
- Accurately estimated fault locations between simulated line segments.
- Demonstrated effective real-time monitoring on ESP32 serial interface.
