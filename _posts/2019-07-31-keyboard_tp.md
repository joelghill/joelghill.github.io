---
layout: post
title:  "MacBook Pro Trackpad and Keyboard"
date:   2019-07-31
categories: [apple_pi]
tags: [Raspberry-Pi, MacBook, A1286, Cypress] 
---
At this point the keyboard an trackpad are likely the most complex integrations with the Raspberry Pi that I'm going to have to deal with. The computers power button is actually connected to the keyboard which is something I want to reuse, and the trackpad is a complicated electronic component that I will have a difficult time reverse engineering.
<!--more-->
If you look closely at the connections on the motherboard (trackpad on the left, keyboard on the right) you can see they both connect to the integrated circuit (IC) in the middle:
![Left: Trackpad connection. Right: keyboard](/assets\images\keyboard_trackpad_components.jpg)

A closer look at the Trackpad connector...
![Trackpad connector](/assets\images\trackpad_connection.jpg)

... and the keyboard ribbon:
![Keyboard ribbon cable](/assets\images\keyboard_ribbon.jpg)

Luckily, the schematics I mentioned in my last post have detailed how they are both controlled. The IC serves as a [serial peripheral interface](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface) host to the trackpad, a keyboard scanner, and exposes a USB interface to whatever device you want to connect to them. The IC in question is the [CY8C24794-24LTXI](https://www.cypress.com/part/cy8c24794-24ltxi) developed by the Cypress Semiconductor Corp.

The schematic of the Cypress CY8C24794-24LTXI (references to the "Z2" appear to be the trackpad):

![CY8C24794-24LTXI schematic](/assets\images\cypress_schematic.png)

The schematic of the keyboard connections:

![MacBook Pro keyboard pin connections](/assets\images\keyboard_connector.png)

Given that both the CY8C24794-24LTXI and its respective development kit are still available for purchase from Cypress at a very reasonable price, I think I have several options for connecting the keyboard and trackpad to the Raspberry Pi:

1. Use the development kit to connect to the existing IC on the motherboard and read the controller program. I can then print my own PBC with a CY8C24794-24LTXI IC, the appropriate sockets, and flash the controller code to it. If it all goes well I should end up with a Keyboard/Trackpad controller with the actual software and hardware used by Apple.

2. Exact same plan as above, except rather than flashing the original program into a new IC, I remove the IC on the motherboard and use it instead. This should result in a working controller that suits my needs, however I have no backup in case it fails sometime in the future.

3. Develop a breakout board for the keyboard and trackpad connections and reverse engineer a controller for both components.

At this point I prefer the first option. It's less work for me, relatively cheap, and is probably the best bet I have for a complete integration with the keyboard and trackpad. 

I've purchased the [PSoC MiniProg1](https://www.cypress.com/documentation/development-kitsboards/cy3217-miniprog1), the development kit for the CY8C24794-24LTXI family of circuits, and I will provide an update after my attempt at connecting to the IC on the MacBook motherboard!

