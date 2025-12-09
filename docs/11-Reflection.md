---
title: Reflection
---

# Lessons Learned

The following are the top 10 key takeaways our team learned from working on this project.

- Working with real hardware showed how even small wiring mistakes, like a loose ground connection or crossed signal wires, can cause big problems like erratic sensor readings or motor stalls, so careful hardware checks, multimeter verification, and clear labeling of every wire became essential for reliable testing and debugging.
- Planning software with diagrams and states before writing code made it much easier to organize features like automatic curtain control and avoid "spaghetti code" as the project grew more complex with multiple sensors and inter-board communication.
- Version control with Git and frequent commits helped the team track every change, easily roll back mistakes during integration, and understand exactly who changed what when reviewing code history or troubleshooting bugs.
- Clear communication inside the team, especially about pin assignments, ADC scaling, and connector interfaces, prevented many frustrating integration bugs between Mihir's hub board and the sensor boards from Zane and Adrian.
- Testing early and often, starting with individual sensors, then connectors, then full system demos exposed issues with thresholds, motor timing, and signal noise well before the final deadline, reducing last-minute stress and rework.
- Writing simple, focused functions (like separate ones for ADC reading, motor control, and state transitions) instead of cramming everything into long main loops made debugging, testing individual pieces, and reusing code much easier throughout development.
- Data sheets and reference manuals for the PIC18F57Q43, sensors, and motor driver were critical resources, taking time to read them upfront about ADC configuration, PWM settings, and pin functions saved hours of trial-and-error experimentation later.
- Building in basic error handling and fallback modes, like ignoring bad sensor readings or switching to manual button control when a subsystem fails, improved the system's robustness and made live demos much smoother, even when hardware acted up unexpectedly.
- Using a consistent naming scheme for signals (like temp_adc_raw, light_threshold), files (mihir_main.c, sensor_read.c), and functions (read_temperature(), drive_motor_ccw()) helped keep the whole project understandable for all team members, even when reviewing each other's code.
- Time management and breaking the work into small milestones like "connector design complete by week 4," "basic motor control by week 6", made it easier to balance hardware prototyping, coding, integration testing, and documentation throughout the busy semester.

---

# Recommendation for Future Students

- **Start learning the PIC microcontroller toolchain early:** Get MPLAB X IDE, MCC code generator, and the PIC18F57Q43 Curiosity Nano board set up during the first week, and practice basic blink/ADC examples so you're not fighting installation and debugger issues when real project deadlines hit.
- **Practice embedded C programming basics before class:** Get comfortable with pointers for ADC buffers, structs for sensor data, interrupt handlers, and bit manipulation for pin control, these concepts are everywhere in microcontroller code and much harder to learn under project pressure.
- **Use Git version control from day one:** Commit frequently with clear messages like "Added temperature ADC scaling" and use branches for new features so you can safely experiment with motor timing or sensor thresholds without breaking the main working code.
- **Read data sheets carefully and build test circuits early:** Study the PIC datasheet for your pin functions and peripherals, then prototype each sensor (temperature, photoresistor, motion) on a breadboard with simple test code before committing to final PCBs, waiting until integration week leads to cascading hardware fixes.
- **Communicate constantly with teammates about interfaces:** Agree early and document pinouts, expected ADC voltage ranges (0-5V), signal meanings, and timing expectations in a shared spec sheet or README, then test inter-board connections weekly vague assumptions about "that digital pin" cause weeks of debugging pain.