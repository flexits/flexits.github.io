---
layout: post
title: "ServiceDb - a mini-CRM for a repair shop"
thumbnail: "/assets/servicedb/main.png"
categories: desktop
tags: [C#, Windows Forms, FastReports, SQLite, ASP.NET Core, EF Core, REST API]
excerpt_separator: <!--more-->
---

![ServiceDb main window screenshot](/assets/servicedb/main.png)

The self-hosted client-server application is designed to manage and track orders. It consists of two parts: a server and a client. The server is a cross-platform ASP.NET Core application that provides a REST HTTP API. On Windows, it is installed as a system service and includes a configuration utility. The client is a Windows Forms application that, in addition to standard CRUD operations, offers an extensive filtering system and report printing capabilities.

<!--more-->

This project began in the mid-2010s when I was running a small electronics repair shop as a self-employed technician. Initially, it was a single-user desktop application. Dissatisfied with the spaghetti code and limited functionality, I decided to refactor it as I gained more programming experience. Eventually, I realized it would be easier to start from scratch.

Today, the system is a multi-user, cross-platform Web API server with no external dependencies except the .NET runtime. It uses an _SQLite_ database (though switching to something more appropriate is straightforward) with _Entity Framework Core_ for object mapping. Security is implemented using the conventional JWT bearer authentication scheme, with two access levels: standard users and administrators.

While the primary target for the server is Windows systems, I have also tested it on macOS and several Linux distributions. The server is installed as a system service and runs without user interaction. A configuration utility and a _Windows Installer_ package are provided for ease of setup.

The included client application is Windows-only. However, the system is not limited to this platform due to its HTTP REST API, which can be consumed by any application on any platform.

![ServiceDb order edit window](/assets/servicedb/order.png)

The application comes with a set of predefined print documents and allows users to add their own ones. It uses _Fast Reports_ as the print forms engine and renders previews in plain HTML, so no additional software beyond a standard browser is required on the client PC.

![ServiceDb printing forms](/assets/servicedb/printform.png)

Both the server and client share a cross-platform licensing mechanism. It generates hardware-based unique IDs and verifies digitally signed licenses using the _Standard.Licensing_ library.

## Technical

Server side: C#, ASP.NET Core Web API with Authentication, EF Core ORM, Standard.Licensing.  
Client app: C#, Windows Forms, Fast Reports Community Edition.

## Project link

<a href="http://servicedb.flexits.info" target="_blank">
  ServiceDb Homepage
</a>
