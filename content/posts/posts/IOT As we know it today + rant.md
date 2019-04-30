---
date: 2016-10-31T10:58:08-04:00
description: "IOT As we know it today + rant"
featured_image: "/images/Pope-Edouard-de-Beaumont-1844.jpg"
tags: ["IOT"]
title: "IOT As we know it today + rant"
---

There are well over 6.4 billion connected devices out there today. with an expectation of 20.8 billion by 2020.[^1]

Well thats great. And I can definitely understand why you would want to have a DVR or an HVAC system that's "smart". When you are leaving from work you can record your favourite show or turn up the heating. It's great if you can do those things remotely. But are they really that secure? 

<h3>The insecurities of Things (IOT) </h3>
 The only thing you might notice as a normal "average" consumer might be an ssl error for a self-signed SSL certificate. 

<figure>
<img src="https://c3.staticflickr.com/6/5746/30396127570_7d2c45b788_b.jpg" class="img-responsive"
<figcaption>self-signed SSL error</figcaption>
</figure> 

But even big corporations use self-signed ssl certificates for internal use. So it's not really that big of a deal. But let's say we want to secure our home. Ok, let's get some cameras and a DVR. oh wait it has a remote option. And ooh look at that it has password protection by default. 
Yeah. About that. 

It's probably Admin, Admin. or User and Admin.

And there goes your password security. 

<h4>Let's creep people out. </h4>
Let's start with a tv that turns it self on and off and changes channels out of its own. 

<figure>
<img src="https://c3.staticflickr.com/6/5658/30064466754_cba6814834_b.jpg" class="img-responsive"
<figcaption>Dreambox remote control interface</figcaption>
</figure> 

Done!

Ok let's see how our wind turbine is doing

<figure>
<img src="https://c1.staticflickr.com/6/5763/30579541392_5aab7eaca9_b.jpg" class="img-responsive"
<figcaption>An Xzeres wind turbine</figcaption>
</figure> 

And the list of insecure devices continues. The most notorious devices would be security cameras, Baby cams, industrial control systems such as SCADA and BACNET.

<h4>Ok, there on the internet. But there not evil. right? </h4>

Not really. Not only is the Front-end of these devices poorly secured. But the back-end as well. Most of these IOT devices use Linux. Why? It's free and it does everything that you need it to do. But some of these devices take the user input and process it directly in the shell as ROOT. Yes as ROOT! Or even better, some even have ssh or telnet on by default using admin, admin as a login.

Hmm, Big DDOS network anyone? 

<figure>
<img src="https://www.mdsec.co.uk/wp-content/uploads/2016/10/botnet.jpg" class="img-responsive"
<figcaption>&copy; mdsec</figcaption>
</figure> 

> An IoT botnet is partly behind Friday's massive DDOS attack -PCWorld

yup, they used IOT devices in a DDOS attack. oh well. Time to secure your network!

<h4>The Intranet of Things</h4>
- Smart devices are cool. But keep them on the internal network ONLY.

- Need to connect to them remotely. Use a (properly set up) VPN server instead. That then connects to your internal network.

- use a firewall 

- Update all your devices Software and firmware.

And if everyone follows these rules that internet will be a much better and safer place.

<h4>Conclusion of the day</h4>
IOT is cool. But the people who use it need to be educated. And manufacturers need to inform people whats on by default.  

[^1]:Statistics according to [Gartner](http://www.gartneiner.com/newsroom/id/3165317)
