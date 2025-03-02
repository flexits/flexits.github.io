---
layout: post
title: "CNC adapter for plasma cutter"
thumbnail: "/assets/cnc.jpg"
categories: electronics
tags: [electronics, KiCAD]
excerpt_separator: <!--more-->
---

![Installed PCB photo](/assets/cnc.jpg)

A universal interface adapter to ensure interconnection between a plasma cutter power source and a CNC control computer. Provides arc voltage feedback signal with spike filtering and overvoltage protection. Contains a voltage divider for compatibility with different height control modules requirements.

<!--more-->

The PCB is single-sided and coated with lacquer to improve insulation in dirty environments.

## Technical

The board is designed using *KiCAD*. Assembly and testing drawings were created in *Inkscape*.

The schematic itself is rather trivial. Input overvoltage protection is ensured by MOVs, output is protected with a TVS. Filtering is achieved with X and Y capacitors and LC circuits. Current limiting and signal reduction circuit comprises a handful of resistors. Due to high voltage spikes, PCB creepage and clearance distances are increased and the resistors are selected with their maximum allowable voltage ratings in mind.

### Sudden discovery

There are a number of commonly used voltage division ratios, such as 1:20, 1:50, etc. Depending on the required ratio, the resistor values on the adapter board need to be adjusted. However, we can't use a resistor for every calculated value because we're limited to standard EIA values. This is why we use two or three resistors connected in series. A manual brute force search for possible pairs and triples is tedious, so I developed an algorithm to automate the task.
