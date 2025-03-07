---
layout: post
title: "Reversing and emulating a Liposonix cartridge"
thumbnail: "/assets/lipo_reverse.jpg"
categories: [publication, electronics, embedded]
tags: [C, AVR, PIC, KiCAD, Proteus, electronics]
excerpt_separator: <!--more-->
---

![Article screenshot](/assets/lipo_reverse.jpg)

The goal of this project was to create an emulator for the original disposable cartridge used in the Liposonix machine. I reverse-engineered the communication protocol and developed a compatible firmware using an ATMega (a smallish PIC, later) MCU. This work was summarized in an article published by _Хакер_ magazine.<!--more-->

## Technical

First, I traced the schematics of the original cartridge board and attempted to identify the IC but couldn’t find a match. Next, I used a _Saleae Logic_ analyzer to capture the communication between the cartridge and the machine. Based on this data, I coded a compatible replacement, initially using an ATMega (Proteus simulation and real hardware) for debugging and later switching to a PIC12 for production.

The emulator exchanges binary data packets with the machine. It stores cartridge-specific parameters and an operation cycle counter in the MCU's EEPROM. To improve usability, I extended the protocol with new commands to reset the counter and adjust the saved parameters.

The final step was designing a PCB with compatible dimensions to fit the original cartridge case. This was accomplished using _KiCAD_.

![Emulator PCB](/assets/lipo_board.png)

## Project link

<a href="https://xakep.ru/2024/04/11/liposonix-hack/" target="_blank">
  Хакер magazine article
</a>
