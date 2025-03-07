---
layout: post
title: "VRD module for welding machine"
thumbnail: "/assets/vrd.png"
categories: electronics
tags: [electronics, KiCAD, Proteus]
excerpt_separator: <!--more-->
---

![Installed PCB photo](/assets/vrd.png)

A VRD (Voltage Reduction Device) significantly lowers the output voltage of a welding machine in idle mode for safety purposes. This module was designed as a plug-in device to equip machines lacking the VRD function from the factory. It is purely analog, with no MCU or digital components.

<!--more-->

## Technical

A practical voltage reduction device must meet two criteria:

- operate only when the machine is idling, without interfering with the welding process,
- ensure certain turn-on delay to ease a follow-up arc ignition.

To accomplish the first, the VRD module monitors the output parameters of the machine. For the second, it incorporates a turn-on hysteresis.

I performed some reverse engineering to identify the proper connection points for integrating the module into the control board of a commercially available welding machine. Although the module was designed for a specific make and model, I aimed to make it as universal as possible. Additionally, keeping the cost low was a priority, so the design uses a minimal number of inexpensive, widely available components on a single-sided PCB.

The board was designed using _KiCAD_ and simulated in _Proteus_. Assembly and testing drawings were created in _Inkscape_.

### Sudden discovery

Designing a comparator circuit with the desired hysteresis was more challenging than it initially seemed, especially for someone like me with a digital background and no experience in analog circuits. I found an excellent explanation in Rohm's R1102A and TI's TIDU020A application notes and used _Excel_ to perform the necessary calculations.
