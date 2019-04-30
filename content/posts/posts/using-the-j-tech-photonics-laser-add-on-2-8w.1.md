---
date: 2017-04-12T11:14:48-04:00
description: "On the X-Carve"
featured_image: ""
tags: [""]
title: "Using the J Tech Photonics Laser add-on (2.8W)"
---
A while back I’ve bought a J Tech Photonics laser add-on for my X-Carve CNC mill. It wasn’t cheap. I paid €405 for the complete set. This included: The laser and driver module, the 3D printed mounting kit + fan and a pair of safety glasses. 
<figure>
<img src="https://cdn.content.ashleyslab.co/laser.jpg" class="img-responsive"
<figcaption>The laser set: taken by <a href="robosavvy.com">Robosavvy</a></figcaption>
</figure> 

<h3>The installation</h3>
<figure>
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/V61Qp0pCAVI?rel=0" frameborder="0" allowfullscreen></iframe>
<figcaption>Mike Merzke at <a href="https://merzkecustomwoodworking.com/">Merzke Custom Woodworking</a>  has made a great video showing his installation of the laser kit to his X Carve.  View it here to see how easy it is to upgrade. </figcaption>
</figure> 

The people over at J-Tech Photonics have a wide verity of guides available for various machines including: The X-carve, the Shapeoko, Stepcraft, Ultimaker, Makerbot and about a dozen more.
The instructions are very well documented. But well they weren’t exactly Ashley proof. more about that later. The driver is mounted onto of the Z carriage. But while installing the included bottom driver mount I noticed that unless you have you have the NEMA 23 stepper motors you will need to modify the mount. I ended up cutting some pieces out it with some cutters. The driver then mounted perfectly on top. The laser and the “trigger” can be either hard-wired are can be connected using some 2 pin Molex connectors. I opted for the last option. And that is where I messed up. The laser and the “trigger” input both use the same 2 pin Molex connector. And that Is how I fried my Arduino that was plugged in to the GRBL shield. Luckily I have some extra Arduino’s laying around. So after A call with the Inventables Helpdesk (These guys are awesome) I’ve flashed GRBL on to a new Arduino. And now I can continue. 

<h3>The laser in Easel</h3>

After the installation was done, I was dying to try it out. So after changing the spindle control from “manual” to “automatic” in Eazel. Then I tried it out and it didn’t look to good. Then I’ve read the actual user guide and realised that I have to focus the laser beam. So after doing that, it worked like a treat. Beside one small issue?

<h3>What about those dots</h3>
<figure>
<img 
src="https://cdn.content.ashleyslab.co/DSC01447.png" class="img-responsive">
<figcaption>The dot's</figcaption>
</figure> 

When using the laser under Easel you will get “dots”. This happens because Easel thinks it uses an actual router with a mill. And you can’t simply turn those on and one to move them. They are lifted up and down to do so. And that is exactly with Easel does with the laser that is why you get those dots. It can be avoided if you use the right software for the job.

<h3>The Software</h3>
<figure>
<img src="https://cdn.content.ashleyslab.co/01.jpg" class="img-responsive">
<figcaption>Can be found in the downloads section</figcaption>
</figure> 


J-Tech Photonics recommends you either use there Inkscape plugin together with the Universal G-code sender. Or that you use the PicLaser and Picsender software (both are paid and are XX$) I ended up using another program called  ‘LX Easy G-code’ which can be found online or on my download page. And best of all it’s for free. But it requires some extra work. This program was meant to engrave/laser images and it was made for a standard GRBL configuration. So that it relies on a preset feed rate and the M03 command to turn the laser on and off. in the normal GRBL config this will work. But it will not work on the Inventables fork of GRBL. Thats why we need to change some things.



You can see the generated code here.
<p><pre>
%
G1 X49.833 Y0.750
M03
G1 X47.167 Y0.750
M05
G0 X10.500 Y0.750
M03
G1 X1.000 Y0.750
M05
....
M30
%
</p></pre>
We now need to change the M03 command to M03 S10000 (The S 10000 is the PWM value)
The M05 command to turn off the laser can stay.

<p><pre>
%
G1 X49.833 Y0.750
M03 S10000 //the changed M03 command
G1 X47.167 Y0.750
M05
G0 X10.500 Y0.750
M03 S10000 //the changed M03 command
G1 X1.000 Y0.750
M05
....
M30
</p></pre>
Now we need to add a feed rate like this:
<p><pre>
%
G0 F620 //This is the added feedrate
G20
G1 X49.833 Y0.750
M03 S10000
G1 X47.167 Y0.750
M05
G0 X10.500 Y0.750
M03 S10000
G1 X1.000 Y0.750
M05
....
M30
</p></pre>
Be sure to add it right under the ‘$’
G20 or G21 these indicate the unit either Inches or milimeters.
G20 is in Inches
G21 is in Mimlimeters
The F620 means 620 mm/sec

And then in the end we use The universal G-code sender to sent the files to GRBL.

And lets engrave away. 
Here are some results: