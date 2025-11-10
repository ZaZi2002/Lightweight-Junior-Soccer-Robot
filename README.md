# ⚽ Junior Lightweight Soccer Robot — Team Vortex

This repository contains documentation, PCB schematics, and firmware code for **Team Vortex**, our entry in **RoboCup Asia-Pacific 2018 (Kish Island)** in the **Junior Soccer Lightweight/Open** league.

---

## 🧠 Project Overview

The **Vortex** robot is a fully autonomous soccer-playing robot designed for the **RoboCupJunior Soccer** competition.  
It integrates advanced mechanical design, precise electronics, and intelligent control algorithms to detect the ball, navigate the field, avoid boundaries, and coordinate with a teammate during matches.

Our design emphasizes:
- **Compact and modular PCBs** for sensors, drivers, and main control.
- **Omnidirectional locomotion** for smooth multi-directional movement.
- **Reliable sensor fusion** combining IR, ultrasonic, and gyroscope data.
- **Efficient power management** and low-noise signal routing.

---

## ⚡ My Role

I served as the **PCB Designer and Electrical Engineer** on the team.  
My main responsibilities included:

- Designing all electronic circuits and routing PCBs in **Altium Designer**.
- Integrating sensors, drivers, and microcontrollers into a unified electrical system.
- Programming and debugging some parts of the code.
- Managing power distribution and ensuring low interference between modules.
- Collaborating with the mechanical team to match PCB geometry with **SolidWorks** body designs.
- Testing and debugging all electrical connections during assembly.

---

## 🧩 Hardware Summary

| Component | Model / Type | Function |
|------------|---------------|-----------|
| **Microcontroller** | ATmega32A | Main control and processing unit |
| **Motor Driver** | L6203 full-bridge | Controls 4 DC motors (up to 5 A) |
| **Motors** | Faulhaber 2224V009SR (9 V, 1000 rpm) | Provides omnidirectional motion |
| **Ball Sensors** | 16× TSOP IR8601 | Detects IR-emitting soccer ball |
| **Gyroscope** | GY-25 | Measures orientation and angular velocity |
| **Ultrasonic Sensors** | SRF02 (×3) | Measures distance to field borders |
| **Out-Line Sensors** | TEMT6000 Phototransistors + LEDs | Detects white boundary lines |
| **Communication Module** | HC-05 Bluetooth | Enables inter-robot communication |
| **Power System** | 9 V Li-ion battery + regulators | Supplies stable voltage to all modules |

---

## ⚙️ Software & Algorithms

- **Programming Language:** C  
- **Compiler:** AVR-GCC  
- **Protocols:** UART, I²C, PWM  
- **Main Control Board:** ATmega32A  
- **Main Features:**
  - 16-direction omnidirectional movement using PWM motor control.
  - Real-time ball tracking and alignment using IR sensor array.
  - Gyro-based orientation correction and goal alignment.
  - Out-line detection and automatic avoidance.
  - Communication between two robots for role assignment (attacker/goalkeeper).

### 🧠 Key Algorithms

- **Motor Control:**  
  Implemented `Motor()` and `Move()` functions for PWM-based speed and direction control.
- **Ball Detection:**  
  16 TSOP sensors processed via ADC for IR signal intensity mapping.
- **Out-Line Avoidance:**  
  Phototransistor layers detect white lines; the robot performs adaptive braking and reversal.
- **Positioning:**  
  SRF02 ultrasonic sensors used to map distance from walls and goals.
- **Goal Orientation:**  
  Gyroscope module (GY-25) with Kalman filtering maintains stable heading.
- **Bluetooth Coordination:**  
  Master-slave communication for deciding which robot attacks or defends.

---

## 🧱 Mechanical Design

- **Material:** Fiberglass for lightweight strength.
- **Frame:** Three circular layers (bottom, disc, top).
- **Motor Holders:** 3D-printed using ABS for strength and weight optimization.
- **Wheels:** Omnidirectional wheels (2.25 cm radius) for smooth lateral motion.

The robot’s 3D model was designed in **SolidWorks**, exported as DWG, and imported into **Altium Designer** for accurate PCB placement.

---

## 🧾 Innovations

- Custom 3-layer PCB system (main control, sensor array, and motor drivers).
- Integration of **GY-25 gyroscope** instead of magnetic compass for noise immunity.
- **Out-line calibration mode**: robot reads and stores white/green thresholds dynamically.
- Modular design simplifying debugging and assembly.

