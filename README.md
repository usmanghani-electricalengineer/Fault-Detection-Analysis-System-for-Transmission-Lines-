# Fault Detection and Analysis System for Transmission Lines
A **real-time monitoring system** designed to detect, classify, and approximately locate faults in **three-phase transmission lines** using an **ESP32 microcontroller** and **CT sensors**.  
Developed as part of my **Final Year Project in Electrical Engineering**.

## Objective
To design a **real-time fault detection and classification system** for transmission lines that can:
- Detect **Line-to-Line**, **Line-to-Ground**, **Overload**, and **Overvoltage** faults  
- **Classify** the type of fault accurately  
- **Estimate** the approximate fault location along the line  
- **Provide rapid fault information** to improve reliability and minimize downtime  

## Working Principle
### Power Supply
- Three **lithium-ion batteries** (≈6.5V combined) provide power to the ESP32 microcontroller.  
### 3-Phase Supply Generation
- A **BLDC motor** with a **speed controller** is used to generate the 3-phase AC supply.
### Measurement & Monitoring
- **CT Sensor (ZMCT103)** measures the current in each phase.  
- One terminal connects to the transmission line, and the other to the ESP32 via a **voltage divider** circuit.
### Fault Simulation
- The transmission line model includes **three towers spaced 150m apart**, each segment having a **1.5Ω resistance**.
### Fault Detection Logic
- The **ESP32 continuously monitors** current and voltage in all three phases.  
- When readings exceed predefined thresholds, the system determines:
  - **Fault Type:** Line-to-Line, Line-to-Ground, Overload, or Overvoltage  
  - **Approximate Fault Location:** Calculated using impedance and voltage drop analysis
  
## Key Highlights
- Real-time fault detection and classification  
- Impedance-based fault location estimation  
- Low-cost implementation using ESP32 and CT sensors  
- Supports multiple fault types (L–L, L–G, Overload, Overvoltage)  
- Modular design for future IoT or cloud integration  

## Components Used
| Component | Description |
|------------|-------------|
| **ESP32** | Main microcontroller for processing |
| **BLDC Motor + Controller** | Generates 3-phase AC supply |
| **CT Sensor (ZMCT103)** | Measures current in each phase |
| **Lithium-ion Batteries (x3)** | Power source (~6.5V total) |
| **Voltage Divider Circuit** | Scales voltage for ESP32 input |
| **Resistors (1.5Ω each)** | Simulates line segment resistance |
| **Transmission Line Model** | 3 towers, each 150m apart |

## Results
- Successfully **detected and classified** Line-to-Line, Line-to-Ground, Overload, and Overvoltage faults.  
- Accurately **estimated fault locations** between simulated line segments.  
- Demonstrated **effective real-time monitoring** via ESP32 serial interface.  
