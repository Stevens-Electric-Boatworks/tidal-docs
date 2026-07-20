---
title: Intro to Tidal Telemetry
---

# Welcome to Tidal Telemetry

Welcome to the Tidal Telemetry platform, built by Stevens Electric Boatworks. The goal of these series of articles is to educate you about the various portions of the control system, the design philosophy behind them, and provide a theoretical foundation before diving into the actual setup and code of the project. 

The 3 core projects are:

* **TidalCore** - The primary control code which aggregates data from the boats sensors, communicates with motor controllers over CAN, records GPS information, and provides a data up-link via cellular to the shore system (TidalShore)
* **TidalShore** - The web based shore monitoring system which provides easy access to all data, server-side redundant data logging, downloading, and parsing, as log files
* **TidalView** - The driver dashboard which runs directly on the boat, giving the driver mission critical information about the boat's systems, as well as providing diagnostics tools when a cellular connection to TidalShore isn't available
 

The project tech stack consists of as follows:

* **C++ & Python** - Used to implement the control system code alongside ROS2 (Robot Operating System)
* **Typescript/JavaScript/React/Tailwind-CSS** - Used to implement the web-based shore system, including the shore server and client
* **Flutter/Dart** - Waterboard is implemented in this language
* **ROS2** - The backbone of the on-boat control system
* **Linux** - ROS2 runs on Linux, as well as being the primary development platform

Each of these form a critical component of the tech stack, and basic knowledge should be known about all parts of the tech stack to be successful.

To get started, continue reading more about the overall system design, as well as the specific subsystems of each part of stack.

