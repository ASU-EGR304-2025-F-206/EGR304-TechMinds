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

### Message Structure and Decisions

- Our message structure is based on the idea that Mihir’s board is the main controller, and Zane and Adrian’s boards are sensor modules. Each sensor board sends information to Mihir using a small, fixed set of signals over the 8‑pin connector.
- The most important messages are the analog sensor values (temperature, light, motion), which are sent as 0–5 V signals into Mihir’s ADC channels. This keeps the messages simple: each voltage level directly represents a physical quantity, and the hub converts it into a useful value in software.
- Digital lines are used only for basic control and status messages, such as “sensor ready,” “fault,” or other simple flags. This choice avoids a complex communication protocol and makes timing easier to handle, because each line has a single, clear meaning.
- The 8‑pin connector is structured so that power, ground, analog signals, and digital signals are always on the same pins for each subsystem. This fixed layout acts like a contract between boards: any future sensor board that follows the same message structure and pinout can plug into the system without changing the main design.

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

---

### Zane's Connector (Temperature Sensor Circuit Connector)

| Pin | From        | To          | Type            | Description                              |
|-----|-------------|-------------|-----------------|------------------------------------------|
| 1   | Mihir (RC4) | Zane (RB1)  | 0–5 V Digital   | Digital control / status signal          |
| 2   | Zane (RB2)  | Mihir (RD0) | 0–5 V Digital   | Digital control / status signal          |
| 3   | Mihir (RD5) | Zane (RD5)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 4   | Mihir (RD6) | Zane (RD6)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 5   | Mihir (RD7) | Zane (RD7)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 6   | Mihir (RB7) | Zane (RA7)  | 0–5 V Analog    | Motion sensor output                     |
| 7   | Zane (RA2)  | Mihir (RA2) | 0–5 V Analog    | Temperature sensor output                |
| 8   | Ground      | Ground      | Ground          | Common ground reference                  |

---

### Adrian's Connector (Photoresistor Sensor Circuit Connector)

| Pin | From        | To          | Type            | Description                              |
|-----|-------------|-------------|-----------------|------------------------------------------|
| 1   | Mihir (RD3) | Zane (RB2)  | 0–5 V Digital   | Digital control / status signal          |
| 2   | Zane (RF0)  | Mihir (RD2) | 0–5 V Digital   | Digital control / status signal          |
| 3   | Mihir (RD5) | Zane (RD5)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 4   | Mihir (RD6) | Zane (RD6)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 5   | Mihir (RD7) | Zane (RD7)  | 0–5 V Digital   | Flex pin (general‑purpose digital I/O)   |
| 6   | Mihir (RB7) | Zane (RB7)  | 0–5 V Analog    | Motion sensor output                     |
| 7   | Zane (RA7)  | Mihir (RA1) | 0–5 V Analog    | Photoresistor sensor output              |
| 8   | Ground      | Ground      | Ground          | Common ground reference                  |


---

### Source Files

- **View the editable draw.io source:**  
  [Open draw.io Diagram](https://drive.google.com/file/d/1H6aJwPv8wPsPnQuJsYAvrDz7MDm43k3i/view?usp=sharing)

- **Download the .drawio file from GitHub repository:**  
  [Download from GitHub](https://github.com/ASU-EGR304-2025-F-206/EGR304-TechMinds/blob/main/docs/images/Teamblockdiagram.png)

---

### Biggest Software Changes Since Proposal

- **Clearer state machine on Mihir’s hub** -
From the beginning, Mihir’s board was the main controller, but the early code used basic if and else logic to decide when to move the curtain. This worked, but it was harder to see all the modes and transitions at once.
The final design makes the curtain behavior more explicit on Mihir’s board by organizing the logic into clearer states (for example, Idle, Opening, Closing, Paused, Error), consistent with the updated UML state diagram. This makes the flow of decisions easier to read and test, even though the hub role itself did not change.

- **More consistent handling of ADC‑based messages** - In the proposal, each board and feature tended to read ADC values in its own way, and some conversions were done locally instead of in a common pattern. This made it harder to keep scaling and thresholds consistent across temperature, light, and motion inputs.
In the final version, the way ADC values are read and interpreted is more consistent with the design shown in the UML diagrams. Each analog message (from temperature, light, or motion circuits) is read into Mihir’s board and processed in a similar pattern, which simplifies calibration and makes the message structure between boards clearer.

- **Cleaner use of inter‑board digital signals** - The proposal allowed for digital connections between boards, but their exact meaning and usage were not clearly defined. This could lead to confusion about what each line represented and when it should be checked.
The final software assigns clearer roles to the digital lines between boards, in line with the updated sequence and interaction diagrams. Each important digital connection now has a defined purpose (such as a specific status or control flag), and the code checks these signals in a more structured way, reducing ambiguity in inter‑board messaging.

- **Added checks for sensor and subsystem problems** - Originally, the code focused mainly on the normal situation where all boards and sensors were connected and working properly. It did not handle unusual values or missing inputs in a structured way.
In the final design, Mihir’s software includes more checks around the ADC readings and inter‑board messages. If a sensor signal is outside a reasonable range or a board appears inactive, the software can take safer actions (such as stopping the motor, ignoring that input, or relying on local control), improving real‑world robustness.

- **Smoother interaction between automatic logic and buttons** - In the earlier design, button inputs could interfere with ongoing automatic decisions, sometimes leading to awkward or sudden changes in curtain movement. The behavior of manual overrides compared to automatic mode was not fully worked out.
The updated software, reflected in the UML diagrams, treats button presses more carefully so they work better with the existing states and messages. Button actions are interpreted in a way that makes transitions between automatic operation and manual control smoother and more predictable, while still keeping Mihir’s board as the central decision point.