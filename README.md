🤖 Northrop Grumman Collaboration Project
Unmanned Ground Vehicle (UGV) – Manual Control System

This repository contains the embedded software for the manual control of an Unmanned Ground Vehicle (UGV), designed to meet the specifications set forth by Northrop Grumman. The system enables real-time remote operation of both the vehicle drive system and a multi-joint robotic payload arm.

🧠 System Overview
The UGV consists of two main actuation systems:
1. Controls → DC Motors (drive + steering)
2. DAQ → Servo Motors (payload arm + end effector)

⚙️Controls STM (Actuation)

Responsible for real-time control of the vehicle and payload:

🚗 Drive System
-DC motors with encoder feedback
-Speed control loop
🧭 Steering
-Heading control loop
-Steering servo control
🦾 Payload Actuation
-Servo control for robotic arm and end effector

📡 Sensing STM (Perception)
Responsible for gathering and distributing system feedback:
📊 Sensor Interface
-Ultrasonic sensors
-Low-level sensors
📺 Display Output
🔁 Provides feedback to control system and Jetson

🌐 Communication (UDP / Ethernet)
Communication between Jetson and STM subsystems is handled via:
-UDP over Ethernet (LwIP)
-Jetson ⇄ Controls STM ⇄ Sensing STM

🧵 Real-Time Scheduling

Both STM subsystems run FreeRTOS, enabling:

-Parallel task execution
Separation of:
-Control loops
-Networking
-Sensor processing

💡 Ensures deterministic timing and responsiveness.
