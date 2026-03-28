# ZuPSC – NSLS-II Power Supply Controller

The **ZuPSC** is the next-generation NSLS-II Power Supply Controller built on a Zynq UltraScale+ FPGA platform. It combines FPGA-based real-time control with embedded software to deliver high-performance regulation, data acquisition, and system diagnostics.

---

## Overview

- **FPGA (PL)**  
  - Executes PID control loops at the sample rate  
  - Handles high-speed data acquisition  
  - Implements interlock and protection logic  

- **ARM Processor (PS)**  
  - Runs a server interface  
  - Communicates with a custom EPICS driver  
  - Provides control, monitoring, and diagnostics over the controls network  

---

## System Architecture

The ZuPSC chassis is composed of three primary circuit boards:

### 1. FPGA Processing Board (zuDFE)
- NSLS-II standard processing platform  
- Digital I/O and GPIO handling  
- ADC data acquisition  
- 20-bit precision DAC output  
- PID control loop execution in FPGA fabric  
- High-speed and low-speed communication:
  - Ethernet
  - Fiber links  
- Embedded Event Receiver (EVR)
  - Compatible with 2.5 Gbps MRF Event Generator (EVG)

---

### 2. Carrier Board
- Interfaces FPGA processing board to channel electronics  
- Routes signals between digital and analog domains  
- Provides system-level connectivity  

---

### 3. Channel Electronics Board
- Precision analog front-end  
- **20-bit DAC** for power supply command output  
- **Dual 20-bit ADCs** for DCCT readback  
- **4× 16-bit ADCs** for auxiliary monitoring  
- Isolated digital I/O channels  

---

## Key Features

- Real-time PID control implemented in FPGA  
- High-resolution (20-bit) DAC/ADC signal chain  
- Deterministic timing via embedded EVR  
- Integrated interlock and protection logic  
- EPICS-compatible control interface  
- Modular 3-board architecture  

---

## Intended Use

The ZuPSC is designed for high-performance accelerator power supply control applications at NSLS-II, where deterministic timing, precision measurement, and reliable interlocks are critical.
