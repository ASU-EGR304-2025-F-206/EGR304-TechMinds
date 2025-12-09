---
title: Software V2.0 – Proposed Improvements
---

# Software V2.0 Overview

Software V2.0 enhances the intelligence, precision, and reliability of the automated curtain control system by expanding beyond the basic threshold-based logic used in Version 1.0. While the core architecture (distributed PIC18 subsystems communicating through an 8-pin interface) remains consistent, the new software stack introduces advanced control features, smarter decision-making, and improved safety mechanisms.

Version 2.0 leverages new hardware capabilities, including the addition of an encoder, expanded sensing, and optional Wi-Fi connectivity. These upgrades enable more fine-grained motor control, richer system feedback, and enhanced user interaction. The updated software architecture is designed to be modular, scalable, and fault-tolerant, making it easier to extend functionality and integrate future subsystems.

Software V2.0 emphasizes:
- **Precision motor control** using encoder-based position tracking instead of fixed-duration timing  
- **Safety-driven obstruction detection**, stopping the motor if expected encoder counts are not achieved  
- **Adaptive automation logic** that adjusts thresholds based on historical light and temperature trends  
- **Support for remote control and OTA updates** through an integrated Wi-Fi SoC  
- **Cleaner inter-board communication** with standardized message structures and error-checking  
- **Improved debugging & testability** through state logging, diagnostic LEDs, and optional serial output  

These improvements build directly on lessons learned from V1.0 field tests, addressing limitations in timing-based motor movement, fixed automation behavior, and limited user control. The result is a more responsive, user-friendly, and robust smart-curtain system ready for real-world deployment.

---
