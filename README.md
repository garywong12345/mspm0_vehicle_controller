# MSPM0 Embedded Vehicle Control System

## Overview
A tethered, closed-loop vehicle control system built on the Texas Instruments MSPM0 microcontroller. This project implements a Proportional-Integral (PI) control scheme in bare-metal C to dynamically regulate speed and steering via external sensor inputs. 

![Demo Video](link-to-your-portfolio-video-or-gif)

## Hardware Architecture
* **Microcontroller:** LP-MSPM0G3507 Launchpad Development Board
* **Chassis:** RPI-RSLK Robotic Car (RSLK)
* **Sensors/Inputs:** Breadboard remote featuring analog potentiometers.
* **Actuation:** PWM signal generation driving motor controllers.

## Software & Toolchain
* **Language:** C (Bare-metal)
* **IDE:** Code Composer Studio (CCS)
* **Hardware Abstraction:** Utilized a course-provided Hardware Abstraction Layer (HAL) to interface with the MSPM0 registers.
* **Key Implementations:** 
  * Configured hardware-level GPIO and ADC initializations to read analog remote inputs.
  * Executed a PI control loop to minimize steady-state error in vehicle trajectory.
  * Implemented speed and turning control to allow for reversing and sharp turns.

## Team & Contributions
This project was developed collaboratively with Kyle Kuan. 
* **My Contributions:** Programmed the core PI control loop in C, implemented the breadboard controller, and implemented the dynamic PWM logic for steering and speed regulation.
* **Kyle Kuan's Contributions:** Derived the mathematical equations to calculate real-time velocity from hardware encoder signals, collaborated on tuning the PI control loop gains, and executed system-wide debugging.

## How to Build and Flash
1. Clone this repository: `git clone https://github.com/garywong12345/mspm0_vehicle_controller.git`
2. Import the project folder into **Code Composer Studio**.
3. Ensure the MSPM0 LaunchPad is connected via USB.
4. Build the project and flash the binary using the CCS Debug probe.

## Key Learnings & Debugging
* **Hardware-Software Boundary:** Resolved initial jitter in motor response by tuning the Proportional and Integral gains within the control loop and implementing basic software debouncing for the breadboard push-buttons.