# Problem Statement: Autonomous Self-Balancing Pick & Drop Robot

**The Core Challenge: Spatial Inefficiency in Material Handling**
Traditional robotic platforms deployed for logistics, autonomous pick-and-place operations, and industrial material handling predominantly rely on four-wheeled, three-wheeled, or tracked chassis designs. While stable, these platforms require significant floor space, possess large turning radii, and struggle to navigate narrow corridors or dynamically changing environments. 

**The Technical Barrier: Dynamic Payload Stability**
Reducing a robot's footprint to a two-wheeled inverted pendulum solves spatial constraints by enabling a zero-degree turning radius. However, introducing a mechanical manipulator (arm and gripper) to a two-wheeled base introduces a critical physics problem. Picking up, carrying, extending, and dropping payloads continuously shifts the system’s Center of Gravity (CoG). Standard static balancing algorithms fail under these conditions, causing the robot to overcompensate and fall when a load is applied or released.

**The Solution: DAVIDPUTRA 3000**
Team Decepticons engineered this two-wheeled autonomous system as a proof-of-concept for highly maneuverable, space-efficient material handling that dynamically adapts to weight shifts.

### Key Objectives & Innovations

* **Zero-Radius Maneuverability:** Utilizing a two-wheeled differential drive system to operate in ultra-tight workspaces where traditional logistics robots cannot fit.
* **Dynamic CoG Compensation:** Implementing a real-time auto-trim PID loop that monitors continuous motor effort and automatically adjusts the target balance angle ($\theta_{\text{trim}}$) to counteract the forward or backward weight bias of different payloads.
* **Jerk-Free Actuation:** Applying slew-rate limited servo profiling (1° per 15 ms) to ensure the 2-DOF mechanical arm movements during automated pick-and-drop sequences do not impart destabilizing kinetic energy to the inverted pendulum.
* **Asynchronous Control Architecture:** Isolating the 200 Hz IMU sensor fusion and stabilization math on a dedicated processor core, ensuring external wireless commands and web dashboard traffic never interrupt the robot's dynamic equilibrium.