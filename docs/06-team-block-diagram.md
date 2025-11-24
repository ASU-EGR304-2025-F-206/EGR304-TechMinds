---
title: Team Block Diagram
---

# Intro / Overview
The block diagram shows the system for our automatic curtain raiser designed by TechMinds. The diagram illustrates how each team member’s system interacts through a standardized 8-pin connector, giving a seamless connection and functionality between boards. Each team member was responsible for an individual subsystem based on the Microchip PIC18F57Q43 Curiosity Nano. The design follows a hub-and-spoke connection, where the lines are shared through the defined digital and analog channels.

---

## Subsystem Roles

### Mihir’s Subsystem — System Hub + Actuation
- Central control and decision-making unit
- Receives analog input signals from other subsystems
- Drives the motor using an H-bridge
- Controls a status indicator LED
- Includes a button and local sensing for standalone operation

### Zane’s Subsystem — Environmental Sensing + Signal Output
- Interfaces with a temperature sensor and amplification circuit
- Processes the measured signal for use by Mihir’s subsystem
- Provides output to shared analog connections
- Includes a button and LED for isolated testing

### Adrian’s Subsystem — Light-Based Interaction + Local Inputs
- Measures light levels using a photoresistor and op-amp
- Sends processed light-level signal to Mihir’s subsystem
- Includes a button and LED for independent functionality

> *"**Note:** This division ensures efficient connector usage: only necessary analog signals are shared, digital signals stay local, and GND is common across all boards, minimizing inter-board wiring."*

---

## Risk Assessment

| Potential Issue | Impact on System | Mitigation Strategy |
|----------------|-----------------|-------------------|
| Loss of Zane’s subsystem | Environmental sensing disabled | Mihir uses fallback controls |
| Loss of Adrian’s subsystem | Light-based automation unavailable | Curtain operates using other input methods |
| Loss of Mihir’s subsystem | Motor control lost | Other boards maintain limited local function |

---

# Conclusion

This design defines Mihir’s subsystem as the main processing and actuation hub, while Zane and Adrian’s subsystems provide modular environmental inputs. The structure supports simplified testing, modular architecture, and resilient operation when subsystems become unavailable.


![Team 206 Block Diagram](images/Team_206_Block_Diagram.drawio.png)

### Source Files

- **View the editable draw.io source:**  
  [Open draw.io Diagram](https://drive.google.com/file/d/1H6aJwPv8wPsPnQuJsYAvrDz7MDm43k3i/view?usp=sharing)

- **Download the .drawio file from GitHub repository:**  
  [Download from GitHub](https://github.com/ASU-EGR304-2025-F-206/EGR304-TechMinds/blob/main/docs/images/Teamblockdiagram.png)
