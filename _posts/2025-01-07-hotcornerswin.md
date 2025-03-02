---
layout: post
title: "HotCornersWin - bring macOS hot corners into Windows"
thumbnail: "/assets/hotcornerswin.png"
categories: desktop
tags: [C#, Windows Forms]
excerpt_separator: <!--more-->
---
![HotCornersWin main window screenshot](/assets/hotcornerswin.png)
*70+ ⭐ on GitHub and counting!*  
This app allows you to trigger a predefined action by moving the mouse cursor into a corner of the screen. For example, setting it up to invoke *Task View* (usually activated by `Win+Tab`) provides a Windows alternative to macOS's *Mission Control*.
<!--more-->

You can assign different actions to each corner independently or leave some corners without any action. The app includes a variety of predefined actions, as well as an *Action Editor* for creating custom actions. You can assign anything that works in the Windows Run dialog (`Win+R`), such as an executable file, a [URI](https://learn.microsoft.com/en-us/windows/uwp/launch-resume/launch-settings-app?WT.mc_id=WD-MVP-5000693#ms-settings-uri-scheme-reference), or a [CLSID-pointed folder](https://www.autohotkey.com/docs/v1/misc/CLSID-List.htm).

The app is highly customizable: you can adjust the action-triggering delay and the sensitive corner zone radius. It also supports multi-monitor setups, automatically detects full-screen applications to minimize interference, and includes theming support. Additionally, it offers a portable version and is lightweight and fast, with a size of only around 1.5 MB.

## Technical

*Windows Forms* and *Visual Studio*. A bit of unmanaged WinAPI code inside.

## Project link

<a href="https://github.com/flexits/HotCornersWin" target="_blank">
  <i class="fab fa-github fa-2x" title="View on GitHub"></i>
</a>
