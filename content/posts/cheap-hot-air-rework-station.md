---
date: 2016-09-21T11:14:48-04:00
description: "From our friends from China"
featured_image: "https://c1.staticflickr.com/9/8735/28167745144_ebd7210346.jpg"
tags: [""]
title: "Cheap Hot Air Rework Station (with teardown)"
---
A long time ago I've found myself in need for a Hot Air Rework Station. Then the search on Amazon and other sites started. The Hakko ones are a bit pricy and the JBC's are way to expensive. Aliexpress to the rescue. 

<figure>
<img src="https://cdn.content.ashleyslab.co/screenshots/Screen%20Shot%202016-10-16%20at%2011.07.00.png" class="img-responsive"
<figcaption>A 858D on  <a href="https://goo.gl/nGXUDU">Aliexpress</a></figcaption>
</figure> 

And then I saw this. I thought for 50€ why not?
It might not be the best but eh, what could go wrong.

One of the first things you do when you buy something from China that plugs in to the mains is to take it to bits. So that's what I did. 

<figure>
<img src="https://c5.staticflickr.com/9/8517/28500987060_ceb3b7c534_c.jpg" class="img-responsive"
</figure> 

<figure>
<img src="https://c1.staticflickr.com/9/8594/28167747384_7617d01910_c.jpg" class="img-responsive"
</figure> 

<figure>
<img src="https://c5.staticflickr.com/9/8796/28753844756_df9de39e21_c.jpg" class="img-responsive"
</figure> 
<figure>
<img src="https://c8.staticflickr.com/9/8345/28708294751_525e0f5cbe_c.jpg" class="img-responsive"
</figure> 
<figure>
<img src="https://c2.staticflickr.com/9/8249/28170621753_fe7eaf7dca_c.jpg" class="img-responsive"
</figure> 
<figure>
<img src="https://c1.staticflickr.com/9/8738/28753819696_6e983c1326_c.jpg" class="img-responsive"
</figure> 
<figure>
<img src="https://c4.staticflickr.com/9/8648/28708289411_0a71d9d62f_c.jpg" class="img-responsive"
</figure> 

So as you may have seen from the teardown. The main brains in this Rework Station is a ATmega 8 (You can download a copy of the chips contents in HEX format [here](https://drive.google.com/open?id=0B-xPnYpkOVsYZlZwa3I5amNQems)). It also has two power supplies: one using the transformer to power the controls. and one thats based on a capacitive dropper to power the heating element. The construction and solder quality are reasonable. Although there are a lot of flux residues left behind. 

<h2>Does it desolder?</h2> 
Short answer. Yes, It does! However its not a HAKO or a JBC so it does take a bit longer to heat up multilayer boards. But it works excellent especially considering the low price point of this thing. I have successfully desoldered and desoldered: BGA chips, SOIC chips, DPAK's and a lot more. I've set mine to 360°C and and airflow of 7 for big ground planes and 4-6 for tiny components such as a 0805, 0402 resistors and capacitors.  

<h2>Final thoughts</h2>

This is one of the better Hot air Rework Stations if you are on a budget. It isn't perfect, but it works!