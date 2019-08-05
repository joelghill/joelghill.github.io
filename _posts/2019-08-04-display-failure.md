---
layout: post
title:  "Using the MacBook Display: Why Do I Smell Smoke?"
date:   2019-07-26
categories: [apple_pi, failures]
tags: [Raspberry-Pi, MacBook, A1286, Fail] 
---
I screwed up... let's start at the beginning though.

I've actually made some progress integrating the Raspberry Pi to the MacBook Pro display. As it turns out, eBay is a fantastic resource for niche electronic components. After a bit of searching I was able to discover the make and model of the MacBook display (LTN154MT07-G01), as well as a [dedicated controller board kit.](https://www.ebay.com/itm/RTD2270-LED-LCD-Controller-Board-Kit-For-DIY-15-4-Screen-LP154WP4-TLA1-1440x900/182754823373?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)

Now, if you're paying close attention, you'll see my first mistake; *I bought the wrong controller.* Oops.

Fast forward a few weeks and I've gotten the controller in the mail and it's time to disassemble the display! This was mostly a straight forward process, but I'd recommend looking up a dedicated guide.

The trickiest part for me was removing the front aluminum face from the display assembly in order to get to the LCD panel. I ended up using a heat gun to soften the adhesive and a phone repair kit to slowly pry the component away from the frame. 

![This took a long time](/assets\images\macbook_display_disessemble.jpg)

As careful as I was, I still managed to slightly bend the thin aluminum face and it may be noticeable after I put it all back together. If I were to go back and try again I would take my time and *really* heat up the adhesive so it gave way with less force. 

Once the face was off I removed the rest of the screws and pulled out the LCD panel. I was excited to try it out with the controller board, so I immediately connected my PC to the board via VGA, plugged the controller into a 12V adapter I had laying around, then plugged the LVDS cable into the display.

Nothing.

I though that maybe I plugged the ribbon cable into the display upside down so I flipped the ribbon around and tried again... still nothing.

It's at this point I take a closer look at the controller board and I see that it has a dip switch set to "5V" and that there's an option for 12V that I could use instead. Naturally I immediately flip the switch and.... still nothing! 

At least at first.

About 3 seconds later I smell burning and see a thin trail of smoke emanating from the display. Yeah, I screwed up. I can't actually tell what component failed for sure, but the smoke came from here:

![It smells like failure too](/assets\images\broken_display.jpg)

As it turns out, I bought the wrong controller which is why the display wasn't working, and then  proceeded to destroy the display by using the incorrect power setting.

I've since purchased a refurbished display replacement (because there's no way the one I have is going to work now) and the [**correct** controller board.](https://www.ebay.com/itm/NT68676-HDMI-DVI-VGA-LCD-Controller-Board-for-1680X1050-Panel-LTN154MT07-G01/123585092400?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) The new components will arrive in the mail and I'll try again then!



