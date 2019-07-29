---
layout: post
title:  "I found Schematics!"
date:   2019-07-29
comments: true
categories: [apple_pi]
tags: [Raspberry-Pi, MacBook, A1286] 
---

I'm actually still playing catch up on documenting my progress with the Apple Pi so this is actually a bit of an older update. However, I wanted to write a dedicated post on my most important discovery so far: **The full schematics and board view for my Macbook Pro (model A1286)!**

![YAAAAASSSSS!](/assets/images/board_view.png)

To be honest, once I knew the model number for my machine it wasn't hard to track down these files after a bit of Googling. They are the property of Apple, so I'm not going to directly share or link to the documents, but if you try hard enough I'm sure you can find them if you need to.

They have been *invaluable*, and I don't know what progress I could make without them. The schematics detail the circuit designs for all of the internal components, and the board view is a PCB design file I can use to locate the parts listed in the schematics on the actual physical device. 

I've been using [OpenBoardview](http://openboardview.org/) to view the BRD files. It's an open source project that reads FZ (with key), BRD, BRD2, BDV and BV* formats. It also has a combined search system that finds parts, pins and nets all with a single query. 

I can now start to develop a coherent strategy for integrating with the keyboard and trackpad, and also start thinking about potential power solutions.

