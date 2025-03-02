---
layout: post
title: "ElectroCalc - electronic components marking decoder"
thumbnail: "/assets/electrocalc.png"
categories: mobile
tags: [Dart, Flutter, SQLite, sqflite, provider, electronics]
excerpt_separator: <!--more-->
---

![ElectroCalc app screenshots](/assets/electrocalc.png)

The application decodes color band markings and alphanumeric codes for resistors, capacitors, and fuses. Unlike many other similar apps, ElectroCalc supports a wide range of coding systems and combinations, particularly for capacitors. Last but not least, it features a sleek modern interface.

<!--more-->

Supported coding systems:
- through-hole resistors color codes (3 to 6 bands);
- SMD resistor EIA-96 or reverse (i.e. `01B` or `D03`);
- plain resistance values with or without separators (i.e. `103`, `1202`, `0R02`);
- through-hole inductors 4 band color codes;
- plain capacitance values with or without separators (i.e. `472`, `4703`, `n47`);
- EIA-198 encoded capacitance (i.e. `A7`, `f4`);
- alphanumeric voltage codes for capacitors (i.e. `3A`);
- various combined voltage and capacitance codes from 3 to 5 characters (`EA7`, `jAH`, `E106`, `2A224` etc.) for film, electrolytic, polymer and tantalum capacitors;
- widespread SMD fuses (Bourns, Bel, Littelfuse, Panasonic, Siba, TE Connectivity, Vishay, Matsuo, NIC).

## Technical

Some data is stored in an *SQLite* database accessed via the `sqflite` package, while other conversions are performed using lookup tables encapsulated as static final lists in the corresponding classes. The `provider` package is utilized for state management. All graphics, including the app icon, were created in *Inkscape*.

This is my first hands-on attempt at mobile development outside of a university course, so the code may not be optimal in terms of security, performance, or style. Nevertheless, my goal was to create a real-world, usable application, and I believe this has been achieved. The app has certain practical value, it runs smoothly, and I'm especially proud of the color band selection scrolls — it took me a while to implement this piece of the UI in a nice and simple way (actually, it was the hardest one here).

## Download link

<a href="https://www.rustore.ru/catalog/app/com.flexits.electro_calc" target="_blank">
  <img src="/assets/rustore.svg" alt="Download from RuStore"/>
</a>