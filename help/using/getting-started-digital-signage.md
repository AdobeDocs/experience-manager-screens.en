---
title: Basics Of Digital Signage for [!UICONTROL AEM Screens]
description: Learn the basics of a digital signage project.
exl-id: e3913be2-9028-4773-a034-e16924a71e04
---
# Basics of a Digital Signage Project {#basics-digital-signage}

Before diving into AEM Screens implementation best practices, it is important to think of the project as a digital signage project, instead of a traditional software development.

This section provides recommendations on major key elements that are critical to an AEM Screens project implementation.

## Key Elements in Digital Signage {#key-elements}

The *Key Elements* in a digital signage project are:

![](/help/assets/Elements-Revised.png)

Defining the key elements is essential before implementing a digital signage project:

1. **Hardware**

   Hardware defines what hardware components are ideal for your digital signage project implementation:
   * Does the device have enough storage space to run all variations of the experiences offline?
   * Have you allowed for video cable type and length? And does the device support both the desired resolutions (HD, FullHD, `4K`, and so on) and video codecs I am planning to deploy (h.264, h.265, and so on)
   * Usage of physical copper wire
   * Size of screens
   * Number of screens
     * orientation
     * aspect ratio
     * resolution preference

1. **Connectivity**

   Connectivity emphasizes the following questions:
   * Networked (cell or wi-fi) or standalone?
     * Must you allow for USB content updates?
     * Must you allow for usage of data collection?
  
1. **Installation**

   Installation includes:
   * Displays: landscape or portrait
   * How is the screen mounted?
     * Portrait orientation versus landscape orientation
     * Full housing
     * Cover plate
   * Fixture support
   * Personnel: responsible for installing the equipment and connecting it to the network
   * How far away is the power source from the fixture?
   * How far away is the physical panel from the actual device?

1. **Content**

   Content includes:
   * Single-zone or Multi-zone?
     * How many media assets are on the screen at the same time?
     * How many pages for interactive applications?
     * Define the UI Loop
     * Data Driven content?
   * Version Control
   
1. **Interactive**
  
   Interactive includes:
   * Preferred touchscreen type?(resistive, capacitive, multi-touch)?
     * Button press
     * Gesture
   * Data triggering (I/O)?
     * Sending/Receiving serial commands (contact closure, PLC, and so on)
     * Incoming data goes on the screen (RSS) or triggers content
     * RFID/NFC/Bluetooth/iBeacon
     * External services (weather, traffic)

1. **Environment**

   The environment emphasizes on:
   * Display location?
     * Inside vs. Outside
     * Out-of-reach or directly exposed
   * Special temp requirement?
   * Vandal proof?
   * High ambient light? Strong contrasts?

1. **Maintenance**

   Maintenance emphasizes on:

   * Are installation guides and user guides required?
   * Are you configuring (programming) the device before shipment?
   * Must you capture each serial number for tracking purposes?
   * Are there any back-up power requirements (uninterrupted power supply)?
   * How are system updates deployed? And how are devices monitored remotely? Is an MDM solution required?
