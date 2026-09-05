<img width="8160" height="4592" alt="20250728_182313" src="https://github.com/user-attachments/assets/24275b70-a4a3-45c7-96e2-cfbb6decba7c" /># V//OHM

A fully custom laptop designed and built from scratch around the **LattePanda Mu compute module**. (YOUTUBE VIDEO COMING SOON!)

<img width="3000" height="2843" alt="646677319-aeb9b2ca-0f19-435e-82b2-cb5939ca135d (2)" src="https://github.com/user-attachments/assets/ca599b35-6463-4e02-9272-9e37949c13ed" />

This project started with a simple idea: **could I build my own laptop from the ground up?**

Over the course of about a year, I designed the electronics, custom PCBs, aluminum chassis, keyboard, cooling system, battery system, display assembly, and internal layout before assembling everything into a working computer.

Rather than modifying an existing laptop, almost every part of the system surrounding the compute module was designed specifically for this project.

---

## Overview

The laptop is built around a **LattePanda Mu**, a small x86 compute module powered by an Intel N305 processor. From there, I designed the rest of the system around it.

Some of the major components include:

* Intel N305 LattePanda Mu compute module
* 14-inch 2560 x 1440 display
* Custom 4-layer carrier PCB
* Custom full mechanical keyboard
* NVMe storage and WIFI Card support
* Custom USB audio system
* Custom battery and charging system
* CNC-machined aluminum chassis
* Custom cooling system

<img width="16320" height="12240" alt="Insidelaptop (2)" src="https://github.com/user-attachments/assets/2a6ba1d9-7166-4e25-b9cf-a9fdeb04895b" />

---

## Why I Built It

Before this project, I had experience with programming, robotics, CAD, and basic electronics, but I had never designed something at this scale. I wanted a project that would help me to learn areas of engineering I had never worked with before.

Building a laptop meant learning about high-speed PCB design, power electronics, USB, PCIe, eDP displays, embedded systems, battery management, thermal design, mechanical manufacturing, and system-level debugging.

A lot of the project became a cycle of designing something, discovering why it didn't work, learning more about the problem, and redesigning it.

That process ended up being one of the most valuable parts of the project.

---

# Hardware

## Compute Module

The laptop uses the **LattePanda Mu**, which contains an Intel N305 processor along with the system memory and other core components.

Using a compute module allowed me to focus on designing the hardware surrounding the processor rather than attempting to design a modern x86 motherboard completely from scratch.

The Mu connects to my custom carrier board through its high-density board-to-board connectors.

---

## Custom Carrier PCB

One of the largest parts of the project was designing a custom **4-layer carrier PCB** for the LattePanda Mu.

The board routes many of the interfaces coming from the compute module, including:

* PCIe
* USB 3
* USB 2
* NVMe storage
* WIFI Card Slot
* USB-C
* Power

High-speed interfaces required controlled-impedance differential routing. USB and PCIe differential pairs were routed with their required impedance targets and with attention to pair matching, return paths, and signal integrity. Designing this board was my first experience working with a PCB containing this many high-speed signals.

<img width="1495" height="771" alt="image" src="https://github.com/user-attachments/assets/ad0b5599-7b64-4446-9619-1d53adcbb747" />

<img width="8160" height="4592" alt="20251204_195243" src="https://github.com/user-attachments/assets/c7b6fa52-adc4-470c-8b81-c1f98523b677" />
<img width="8160" height="4592" alt="20251204_195126" src="https://github.com/user-attachments/assets/2ea5d02a-11cd-438b-911e-301461e9390b" />

---

## Display

The laptop uses a **14-inch AUO B140QAN02.3** LCD with:

* 2560 × 1600 resolution
* 60 Hz refresh rate
* 4-lane eDP
* 16:10 aspect ratio

<img width="1600" height="900" alt="WhatsApp Image 2026-09-04 at 10 57 18 PM" src="https://github.com/user-attachments/assets/1e689d5c-277c-45b0-8f73-5a922259d878" />

The panel connects directly to the compute module through an eDP interface.

Integrating the display required designing the cable routing, supplying the correct LCD and backlight voltages, and mechanically fitting the panel into the custom lid.

---

## Keyboard

I designed a custom mechanical keyboard using **Kailh Choc V2 low-profile switches**.

The keyboard uses a matrix layout rather than dedicating an individual microcontroller pin to every key.

The original keyboard electronics were designed around an ATmega32U4 running QMK firmware.

I also had to design the physical keyboard plate and integrate the keyboard into the extremely limited vertical space inside the chassis.

Original Design:
<img width="2040" height="1148" alt="WhatsApp Image 2026-09-04 at 10 57 39 PM" src="https://github.com/user-attachments/assets/01d27412-1f71-4b45-bedb-137f6dbe9358" />

Final Design:
<img width="1148" height="2040" alt="WhatsApp Image 2026-09-04 at 10 57 04 PM" src="https://github.com/user-attachments/assets/a12125d3-7034-4d35-8ed0-af375fd0a8fe" />

---

## I/O

* USB-A
* USB-C
* HDMI
* Ethernet
* SD card
* Power input

<img width="1500" height="2000" alt="WhatsApp Image 2026-09-04 at 10 59 38 PM (1)" src="https://github.com/user-attachments/assets/ef4939e1-324e-49ac-9f4d-23b46347f3e6" />

<img width="1500" height="2000" alt="WhatsApp Image 2026-09-04 at 10 59 38 PM" src="https://github.com/user-attachments/assets/dc9e7b3b-2606-4df6-8546-12d7222d8cd7" />

---

# Power System

Powering the entire laptop required several different voltage rails and power-management circuits.

The system includes circuitry for:

* Battery charging
* Battery protection
* USB-C Power Delivery
* 12 V system power
* 5 V regulation
* Power-path control
* Peripheral power rails

One of the major challenges was making all of these independent systems behave correctly during startup and shutdown.

---

## Battery

The laptop uses a custom **4-series lithium-ion battery pack**. The battery system includes a BMS for cell protection and a dedicated charger. Designing the battery system was especially challenging because the battery had to fit underneath the keyboard while keeping the overall laptop reasonably thin.

---

# Mechanical Design

The entire chassis was designed in CAD.

Onshape link:
https://cad.onshape.com/documents/becc27ed06524a5d0301d2eb/w/d8f227322e85e9de49080e62/e/1cd4a874a6f0ad30a976cb4e

The main chassis uses aluminum components including a CNC-machined bottom section, palmrest, and display lid.

The laptop is approximately **14 inches** across and was designed around the dimensions of the display rather than an existing laptop chassis.

<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/caf37e1c-0407-496c-b8e6-836e27746483" />

A major challenge was packaging everything into the available space. The PCB, battery, keyboard, SSDs, display cable, cooling system, and wiring all compete for only a few millimeters of vertical clearance.


---

# Debugging and Failures

Not everything worked on the first attempt.

In fact, a large part of this project was debugging problems that I had never encountered before.

Some of the issues I had to investigate included:

* Power-rail shorts
* Voltage rails collapsing under load
* High-speed USB problems
* Damaged PCB components
* Connector failures
* Mechanical clearance problems
* Display cable retention
* Cooling and heatsink mounting
* Battery drain
* Manufacturing tolerances

---

# What I Learned

This project exposed me to many areas of engineering that I had never worked with before, including:

* High-speed PCB design
* Differential pair routing
* PCIe
* USB hardware
* eDP displays
* Power electronics
* Battery management
* Embedded systems
* Mechanical CAD
* CNC machining
* Thermal design
* System integration
* Hardware debugging

More importantly, I became much more comfortable approaching technical problems where I initially had no idea what I was doing.

Instead of waiting until I completely understood a subject before building something, I learned to design, test, fail, investigate, and iterate.

That mindset is probably the most important thing I took away from this project.

---

## Tools Used

**Electrical**

* KiCad
* Oscilloscope
* Multimeter
* Soldering / rework equipment

**Mechanical**

* CAD
* CNC machining
* 3D printing

**Firmware / Software**

* C / C++
* QMK
* RP2040 / Pico SDK

---

## Repository

This repository contains documentation, design files, schematics, PCB layouts, CAD files, firmware, and other files from the development of the laptop.

The project is primarily a learning and engineering project rather than a design intended for mass production.
