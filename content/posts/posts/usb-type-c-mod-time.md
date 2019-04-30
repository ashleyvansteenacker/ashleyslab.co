---
date: 2016-06-24T11:15:58-04:00
description: "Taking a USB Type C to A dongle appart"
featured_image: "https://farm5.staticflickr.com/4288/35623543902_d9275b0e57_o.jpg"
tags: []
title: "USB type C Mod time!"
---
<h1>What is type C?</h1>
USB type C is a new way of combining multiple types of connections/signals in to one single connector. For example this single connector contains: a usb 3.0 connection, a usb 2.0 connection, a displayport connection, Analog audio out. And it can both receive and generate power to either charge the device or supply power when your device acts as a "Host" this is truly a magnificent connector.

<h2>Now what has changed compared to usb micro?</h2>
<figure>
<img src="https://qph.ec.quoracdn.net/main-qimg-1cad10158b8ed6bc2a51027a2888d6a4" class="img-responsive" alt="A Nokia branded Micro-A USB port">
<figcaption>A Nokia branded Micro-A USB port: taken by <a href="https://commons.wikimedia.org/wiki/File:A_Micro-A_USB_port.jpeg#/media/File:A_Micro-A_USB_port.jpeg">heaveen</a></figcaption>
</figure>
Usb micro or commonly referred to as mini B only has 5 pins.<strong> VCC, D+, D-, ID, GND </strong> and only has support for a USB 2.O port. Either configured as Device or as Host. 

Now thats all good and well but lets now focus on USB type C!

<figure>
<img src="https://farm5.staticflickr.com/4284/35792163215_5483ddef3d_o.png" class="img-responsive" alt="USB type C pinout">
<figcaption>USB type C pinout: photo by <a href="http://hsto.org/">hsto</a></figcaption>
</figure>
This connector has 2 times 12 pins. now you might have noticed that all the pins on the top (A) row are the mirrored copy of the bottom (B) row. And well yes they are! thats what makes USB C reversable.

<h1>Time to make our own OTG cable</h1>
<figure>
<img src="https://farm5.staticflickr.com/4288/35623603912_c015fe2b08_o.jpg" class="img-responsive" alt="OTG schematic">
<figcaption>OTG schematic: photo by <a href="http://firstpost.com/">Firstpost</a></figcaption>
</figure>
As you can see from this schematic making an adaptor cable is not really that hard. But wait where is that ID pin? The ID pin is no more on the USB C connector. Instead it became Configuration Channel (CC) And well now you need one more component to make your own USB C to A or micro adaptor. 

<h1>Reverse engineering time!</h1>
<figure>
<img src="https://farm5.staticflickr.com/4205/35623577562_8d2cf37bde_o.png" class="img-responsive" alt="GoogleStore C to A cable ">
<figcaption>GoogleStore C to A cable teardown: photo by <a href="https://store.google.com/">Google</a></figcaption>
</figure>

After A lot of cutting trough plastics and heating up the connector to meld the hot glue.
I've finally got a clean PCB. Then using the BigClive photo reverse engineering program I've managed to figure out what does what. 

<figure>
<img src="https://farm5.staticflickr.com/4288/35623543902_d9275b0e57_o.jpg" class="img-responsive"alt="GoogleStore C to A cable teardown">
<figcaption>GoogleStore C to A cable teardown: photo by <a href="https://ashleyslab.co/">Ashley Van Steenacker</a></figcaption>
</figure>

As you can see this one has 4 10µF filter capacitors between Ground and VBUS. And a 5K resistor between the CC pin and the Ground pin. this indicates to the device that it's a OTG device. And that it should generate a 5volt supply on VBUS. 

So now we can make our own  USB C to micro adaptor cable. 
<figure>
<img size=width: 10%;height: auto; src="https://farm5.staticflickr.com/4283/34981942383_2a277f6dda_o.jpg" class="img-responsive" alt="C to micro schematic">
<figcaption>C to micro schematic: photo by <a href="https://ashleyslab.co/">Ashley Van Steenacker</a></figcaption>
</figure>

And now you can make your own USB C OTG cable. I did this teardown so that no one else needs to sacrifice a 15€ USB cable. I'm also looking in to other uses of the USB C connection. So please stay tuned for some more USB C specials. 