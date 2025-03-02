---
layout: post
title: "SerialClient - data acquisition and conversion client"
thumbnail: "/assets/serialclient1.png"
categories: desktop
tags: [C#, Windows Forms, Scintilla.NET]
excerpt_separator: <!--more-->
---

![SerialClient main window screenshot](/assets/serialclient1.png)

While experimenting with embedded devices, I encountered the need for a simple and reliable application to collect various debug data sent by an MCU via its UART interface, while also enabling control and communication. In my projects, I typically use a CSV-like format for sending data and binary packets for exchanging commands. An additional requirement was handling relatively high-speed data streams without causing the application to hang or consume excessive resources (i.e. a 20 byte CSV string each 5 ms is 32 Kb/s stream). Lastly I'd wish to process the acquired data (generate a live plot, for example).
<!--more-->

Unfortunately I failed to find a suitable application that'd be free to use. Most apps I tried either lacked conversion capabilities (for example, the data is frequently displayed only as hex or dec values) or performance (some apps struggled to handle even hundreds of Kb/s streams). This led to the creation of *SerialClient*, which is now capable of:
- displaying incoming data in raw form (as hex, bin, dec values) or parsed with different codepage settings (CP-437, 866, WIN-1251), with optional formatting (spaces between bytes, newlines after certain amount of bytes) almost in real time;
- logging incoming data to a file in either raw binary or parsed text format (raw mode logs can later be used as input);
- using a file as a data input;
- providing a universal plugin interface for further data processing and/or port communication (a plugin gets access to both raw and parsed data and may send data via the currently open port too; there may be a number of plugins active simultaneously);
- contains a visualization plugin for plotting incoming CSV data almost in real time (early beta and somewhat ugly at the time);
- multilingual UI is possible (though only partially implemented because I don't really need it);
- customizable terminal appearance (font, size, color). 

![SerialClient plot plugin screenshot](/assets/serialclient2.png)

## Technical

*Windows Forms* and *Visual Studio*, nothing fancy. I plan to refactor the codebase and use *Avalonia UI* instead to make the app cross-platform and give it a touch of modern visual appearance.

### Sudden discovery

Windows Forms TextBox is extremely slow at updates. After trying some settings combinations abd workarounds that haven't brought success I decided to utilize a 3rd-party component and finally switched to *Scintilla.NET* control.
