---
date: 2016-05-30T11:13:32-04:00
description: "Using the X-Carve"
featured_image: "https://res.cloudinary.com/camperhangouts/image/upload/v1464628694/cover_wcofeh.jpg"
tags: []
title: "DIY solder stencils"
---
So you've made a few printed circuit boards (PCB's) and now you have to manually solder all of those tiny 0402 SMD components. Or you are just curious how you can make your life easier when soldering a lot of SMD components. Search no more!

<h3>It's Stencil time!</h3>

You've probably heard of stencils before and they are everywhere. Think of those: letter stencils, paint stencils and well I can go on with this list until the cows come home. But thats not the point. We want to make our life easier. Thats why we are going to make our own.

<img src="https://res.cloudinary.com/camperhangouts/image/upload/v1464629499/DSC01199_jn5tqo.jpg" class="img-responsive" alt="Just like this">


<h2>Let's do this!</h2>  
So what are you going to need.
<ul>
<li>A Laser (1Watt will be sufficient)</li>
<li>A CNC mill or 3D printer where you can attach the laser to.</li>
<li>.2mm (.0078") plastic (can be found in old LCD's</li>
<li>Depending on your type of laser and material color you may need a permanent marker</li>
</ul>

<h3>Step 1</h3>

Get your design files ready. 
Export the TOP layer as a Gerber. (or directly as a SVG if your PCB design software is capable of doing that)

<h3>Step 2</h3>
Then go to [svgerber](http://svgerber.cousins.io/) to cenvert the gerber file to the SVG

<h3>Step 3</h3>
Import the svg in to easel and then delete all the stuff that you don't need. 

<iframe src="https://drive.google.com/file/d/0B-xPnYpkOVsYOF90bG1SNzM1LUU/preview" width="640" height="480"></iframe>

And then its time to set the correct settings or well at least the one that worked for me. 

Bit size: .6mm
Feedrate: 310mm/min
Depth per pass: .5mm
And the depth of the items to be cut is set at 1mm

The laser power is set to 1W

<h3>Be sure to experiment with this!</h3>
<img src="https://res.cloudinary.com/camperhangouts/image/upload/v1464631675/DSC01200_l39oez.jpg" class="img-responsive" alt="Not deep enough">
This was not deep enough as it was set to:
Depth per pass: 1mm 

<img src="https://res.cloudinary.com/camperhangouts/image/upload/v1464631682/DSC01201_o7dgpu.jpg" class="img-responsive" alt="keep trying">
As you can see the kapton tape didn't work well. But that isn't going to stop me.

I love to see what you make! And if you have found an easier way to do this or have suggestions be sure to comment. 