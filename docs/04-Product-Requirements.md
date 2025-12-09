---
title: Product Requirements
tags:
- tag1
- tag2
---

## Project Objective

The project focuses on investigating and developing adaptive technology to enhance user experience and product design for an automatic curtain opener that utilizes sensors to improve energy efficiency in the home. The goal is to reduce manual operation in the house by utilizing motion and light sensors to adjust the curtains' position based on environmental conditions and user activity. Integrating reliable, low-cost components into this product not only serves to reduce energy consumption but also provides a more accessible solution for individuals with limited mobility. We aim to develop a user-friendly, adaptable, and durable device that demonstrates sensor automation for everyday household tasks, laying the groundwork for smart home innovations.

## Stakeholders

- **Purchasers** – Homeowners, renters, and caregivers determine whether the device suits their space, budget, and installation requirements. Their priorities include simple installation, compatibility with existing           curtain hardware, and no property damage, especially in rentals.

- **Primary users** – People interacting with the device daily, including individuals with mobility limitations, busy parents, shift workers, and people sensitive to bright light/noise. Device success depends on low-effort operation, predictable behavior, and minimal disruption.  

- **Secondary users** – Family members, roommates, and visitors who use the device casually. They need clear feedback cues and fail-safe controls that prevent misuse.  

- **Component suppliers & manufacturers** – Vendors providing key parts like motors, sensors, and electronics. To ensure product reliability, they require precise technical specifications, quality standards, and consistent manufacturing processes.  

- **Maintenance & support teams** – Component suppliers are responsible for motors, sensors, plastics, electronics, and QC. Requirements must define tolerances, material specs, and compatibility.  

- **Retailers & distributors** – These groups focus on strong, protective packaging, smooth logistics, easy returns, and products that earn positive customer feedback to boost sales and brand reputation.

- **End-of-Life/Disposal Stakeholders** – Recyclers, e-waste handlers, and municipal waste services. Materials and modularity must support safe disassembly and recycling of electronic components.

## Use Cases

**User Story #1: Lauren**  
Lauren is a 40-year-old nurse with two small kids. Sleep schedules are unpredictable, mornings are rushed, and she often avoids opening curtains because it wakes the kids. She needs a system that won’t create noise, startle her children, or require her hands to be occupied. Her constraints: limited morning time, frequent multitasking, and the need to control lighting without disturbing sleepers. 

**User Story #2: Michael**  
Michael is a 25-year-old grad student renting his first apartment. He isn’t allowed to drill walls or alter fixtures. He wants automation but has limited setup time and basic tools. He evaluates products based on installation complexity, compatibility with his rental’s curtain rod, and whether the system fits his schedule-based routines.  

## Aspects

The innovative curtain motor product design will be developed based on proven products, along with substantial user and market insights gathered during the research. Priorities are coded **P1 to P10**, with the lowest priority first.

### Hardware / Product Design
- **1.1** – The surface must be smooth with rounded edges to ensure safety, especially in homes with children or pets, minimizing the risk of injury or fabric damage. **(P10)**  
- **1.2** – The device housing shall be made from durable, recyclable materials meeting RoHS environmental standards. **(P9)**  
- **1.3** – Its slim, modern design will fit smoothly into today’s home decor without occupying too much space. **(P8)**  

### Software / Functionality
- **2.1** – The device is to be compatible with a wide range of curtain rods and rails. **(P10)**  
- **2.2** – The device is adjustable to fit different sizes of curtain rods and rails using an adaptor. **(P9)** 
- **2.3** – The device can move heavy curtains without issues by using the remote and app. **(P10)**  
- **2.4** – Connectivity shall include Bluetooth 5.0 and WiFi to ensure seamless control via smartphone app, voice assistants, and home automation hubs (Google, Alexa). **(P10)**  
- **2.5** – The motor shall offer multiple operational modes: QuietDrift for near-silent movement, Normal for everyday use, and Boost to handle heavy curtains or longer distances. **(P9)**  
- **2.6** – Adjustable speed control shall accommodate diverse curtain types and user preferences. **(P8)**  
- **2.7** – The device shall actively monitor for obstructions and automatically stop and reverse if snagging is detected to protect both curtains and hardware. **(P10)**  

### Interactivity & User Experience
- **3.1** – Voice control integration shall support Alexa, Google Assistant, and Siri for hands-free operation, improving accessibility. **(P10)**  
- **3.2** – The user can operate this device remotely or through a free in-app purchase on a smartphone device. **(P9)**  
- **3.3** – The device supports specific ways of operation that ensure minimal disturbances. **(P8)**  
- **3.4** – The product shall provide real-time feedback through LED indicators and app notifications, confirming successful commands or alerting users to errors. **(P9)**  

### Customization
- **4.1** – The device will be offered in at least two colorways, including black and white. **(P7)**  
- **4.2** – The device will offer a custom fit to the railing of the curtain. **(P9)**  
- **4.3** – Adapters and additional accessories will be provided based on the most commonly used curtain rails. **(P8)**  
- **4.4** – Users shall be able to set and save custom curtain positions (e.g., partial open, fully closed) for quick access. **(P9)**  
- **4.5** – The product shall provide adjustable curtain opening and closing speeds to suit different fabric types and user preferences. **(P8)**  
- **4.6** – The system shall allow users to create personalized schedules and routines via the app for automatic operation. **(P9)**  

### Manufacturing & Sustainability
- **5.1** – The device will be durable, meaning the moving parts will be secured and reinforced using injection molding. **(P8)**  
- **5.2** – The device is designed to operate quietly and efficiently using the injection molding manufacturing method. **(P9)**  
- **5.3** – We will use recycled materials made from white ABS and PC plastic for the packaging to ensure safe transportation when shipping the product. **(P6)**  
- **5.4** – The product shall be designed with modular components to simplify assembly, reduce manufacturing time, and facilitate easy repairs or upgrades. **(P9)**  

### Safety
- **6.1** – Overcurrent and overvoltage protection shall be implemented, limiting current to 1.5A and voltage to 5V, avoiding electrical hazards. **(P10)** 
- **6.2** – The product shall include clear safety warnings and user instructions to minimize misuse risks. **(P9)**  
- **6.3** – The device’s moving parts would be secured and reinforced using the injection molding method so the parts do not break while the device is in use. **(P10)**  
- **6.4** – The surface must be smooth with rounded edges to ensure safety. **(P8)**  

## Requirement Criteria Specification

- **1.1.1** – Surface edges shall have a minimum radius of 2 mm to prevent sharp points.  
- **1.2.1** – Device housing shall be RoHS certified.  
- **1.3.1** – Maximum device dimensions shall be 150 mm long and 50 mm in diameter.  
- **2.4.1** – Device shall pair with a smartphone app via Bluetooth 5.0 within 15 seconds in at least 9 out of 10 attempts.  
- **2.5.1** – QuietDrift mode noise level shall be less than 30 dB measured at 1-meter distance.  
- **2.7.1** – Obstruction detection shall stop and reverse the motor within 0.5 seconds of encountering an object.  
- **3.1.1** – Voice command response time shall be under 2 seconds in 95% of trials.  
- **3.4.1** – LED indicators shall visually confirm command execution within 1 second of activation.  

## Open Questions

- Should the device function as a standalone product or connect with existing smart-home systems like Alexa or Google Home?  
- How will the design avoid entanglement with the curtain?  
- How does the environmental impact of the manufacturing process compare to the resources potentially saved?  
- Can we make the product fully recyclable and repairable through design changes, such as ZIF connectors or glue-free assembly?  
- How can we improve battery safety to avoid failures like overheating or self-ignition?  
