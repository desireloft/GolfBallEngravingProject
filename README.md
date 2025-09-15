# Automated Golf Ball Engraving Cell

## Overview

This repository showcases my contribution to a final year group project titled **Building an Automated Golf Ball Engraving Cell**, a collaborative effort to design and implement a fully automated system for cleaning, testing, engraving, and packaging golf balls. The project demonstrates my skills in automation design, system integration, and technical documentation, while adhering to group confidentiality by excluding sensitive materials (e.g., mechanical, electrical, and pneumatic drawings, PLC programs, and robot programs). The cell comprises six stations, controlled by four brands of Programmable Logic Controllers (PLCs) communicating over Ethernet/IP, two robots, and a Human-Machine Interface (HMI) system, with comprehensive safety features. A video demonstration (autoplaying below) highlights the system’s functionality. This project underscores my ability to work in a multidisciplinary team to deliver a complex automation solution, optimized for manufacturing efficiency and safety.

## Project Details

The Automated Golf Ball Engraving Cell is a sophisticated system designed to process golf balls through six sequential stations: Infeed, Washing, Hardness Testing, Sorting, Tubing, and Boxing. The project integrates advanced automation technologies, including PLCs, robotic arms, and an HMI, with a focus on precision, repeatability, and safety. My contributions included [specify your role, e.g., CAD modeling of station components, system integration, HMI design, or safety system implementation], aligning with my expertise in SolidWorks and manufacturing processes.

### System Components

The cell consists of six stations, each performing a specific function in the golf ball processing workflow:

1. **Station 10: Infeed Station with Hopper**
   - Feeds golf balls into the system using a hopper mechanism.
   - Inspired by gumball dispensers for smooth and gravity-assisted ball flow
   - Release of the balls is triggered by a request from Station 20 to maintain continuous operation.
   - Mechanism is optimized for low cycle time to ensure timely feeding of the entire cell without bottlenecks
2. **Station 20: Washing Station**
   - Cleans golf balls to remove dirt and debris, ensuring quality for engraving.
   - Holdback station (station 25) singulates the balls before entering the walking beam (station 30)
3. **Station 30: Hardness Testing Station**
   - Tests golf ball hardness on a walking beam to ensure compliance with quality standards.
   - Walking Beam increments balls forward to the press station,reject and to the engraver pick and place (PNP).
   - The LVDT is used to measure the hardness of the golf ball through the amount of travel with equal force.
   - The piston has been set to 60psi which applies 289 pounds of force to the golf ball
   - The measurement is allowed to settle within a range before being saved as the final value.
   - Station 35 is designed for laser engraving golf balls.
   - A Pick-and-Place (PNP) system will insert two balls into the enclosure and remove two engraved balls.
   - Once the enclosure is closed, both golf balls are engraved simultaneously.
   - fume extractor is used for air filtering
4. **Station 40: Transfer Pick and Place**
   - A Pick-and-Place (PNP) system picks two balls off the walking beam and inserts them into the enclosure and remove two engraved balls.
   - Pick-and-Place then places 2 balls on station 50 to be sorted into tubes.
5. **Station 50: Sorting and Tubing Station**
   - Sorts golf balls based on hardness test results.
   - Based off the press data, golf balls are sorted into three different silos.
   - Three diverting pistons push the golf balls off the track into their respective silo.
   - Once the 3 golf balls have been loaded into a silo, it is ready to drop into an empty tube placed under the funnel.
   - ABB Robot moves the filled tube to the lidding station and lid is placed on the tube.
6. **Station 60: Boxing Station**
   - Station 60 is responsible for packaging tubes into boxes.
   - The UR cobot retrieves a flat-packed box from the magazine and places it into the box erector.
   - The box erector forms the box into shape, preparing it for tube loading.
   - Once the conveyor is available, the UR places the box onto the box locator on the conveyor, where it is re-erected to maintain its shape.
   - After the box is filled with six tubes of golf balls, the conveyor transports the completed box out of the station

### Automation and Control Systems

- **PLCs**:
  - Four brands of PLCs communicate over **Ethernet/IP** for seamless integration:
    - **Siemens**: Controls stations 30 and 40.
    - **Schneider**: Controls stations 10 and 20.
    - **Allen-Bradley CompactLogix**: Acts as the central master PLC, executing critical control decisions for the entire cell.
      - Also used to control stations 50 and 60.
    - **Allen-Bradley Safety PLC**: Oversees safety-related functions, ensuring compliance with safety standards.
  - Ethernet/IP enables robust, real-time communication between PLCs for coordinated operation.
- **Robots**:
  - **ABB Robot**: Handles material transfer between stations (e.g., moving balls from washing to hardness testing).
  - **UR5e (Universal Robots)**: Performs precise tasks, such as engraving or placing balls into tubes.
- **HMI System**:
  - Utilizes **Ignition Vision** for a user-friendly interface to monitor and control the cell.
  - Displays real-time data, system status, and operator controls for efficient operation.

### Safety Considerations

The system incorporates comprehensive safety features to protect operators and ensure compliance with industrial standards:

- **Physical Guarding**: Encloses moving parts to prevent access during operation.
- **E-Stops**: Emergency stop buttons strategically placed for immediate shutdown.
- **Light Curtains**: Detect unauthorized access to hazardous areas, triggering safety protocols.
- **Guard Doors and Locks**: Secure access points with interlocked doors to restrict entry during operation.

### Video Demonstration

The following video showcases the Automated Golf Ball Engraving Cell in action, highlighting the workflow across all six stations, robotic operations, and safety features. The video autoplays for convenience.

<video src="video/NWR-Golf_Ball_Cleaner_demo.mp4" autoplay muted loop width="100%">
  Your browser does not support the video tag.
</video>
*Video: Demonstrates the automated process from infeed to boxing, including robotic handling and safety system integration.*

### Deliverables

Due to the collaborative nature of this group project, sensitive materials (e.g., mechanical, electrical, and pneumatic drawings, PLC programs, and robot programs) cannot be shared.

- The video above provides a visual overview of the system’s functionality.
- All components were designed with manufacturability in mind, supporting processes like machining, welding, or 3D printing.
