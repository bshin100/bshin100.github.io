---
layout: post
title: CNC Router Table
---

> Precision computer-controlled router capable of milling wood, plastic, & aluminum.

### Time frame: June, 2020 - Present

After a few years' experience with a commercial CNC router in my high school robotics shop (a Laguna for those know!), and some more with the vast array of Haas CNC mills at my university, I decided to challenge myself in building a precise and cost-effective CNC router during quarantine 2020.

I am following the open-source platform from V1 Engineering - [the Mostly Printed CNC (MPCNC)](https://www.v1engineering.com/specifications/)
I decided on a build volume of 24" x 18" x 3" which is comparatively small to the 4' x 8' capability of my high school robotics machine, however definitely not needed for the parts I intend to mill. Having a small build volume is important for this design as it utilizes 3D printed components and mild-steel tubing as rails. A machine too large will encounter more vibration, inaccuracy, and begin to meet the rigidity limits of the tubing and plastic. As detailed on the V1 Engineering website, using EMT conduit - normally used for routing electrical wiring in houses and buildings - keeps the costs low, as opposed to the traditional linear rails on a professional machine. A nice upgrade that I wanted to do was to swap in the EMT conduit for some stainless steel tubing, but I couldn't find a local supplier that wasn't super expensive. The stainless steel would provide more rigidity and look nicer. Oh well.

Here's what the CNC Router will look similar to:
![V1 Engineering MPCNC Primo](/images/MPCNC/Primo-scaled.jpg "V1 Engineering MPCNC Primo")

*Note: Throughout the course of the build, a new and improved version of the design was published. Bummer. I was in too deep at this point, so I continued with the last-gen version.

I purchased the components individually (self-sourced) earlier in June and began 3D printing the parts. The dimensional accuracy and structural integrity of these printed parts are pretty important to having a precise machine. I encountered some difficulty with under-extrusion on my 3D printer, which was frustrating since I had about a year of problem-free printing prior to this project. I managed to get all of the parts printed in PLA, using a little over 1.5 kg. Oddly enough, I encountered another 3D printing issue regarding the smoothness of the curved surfaces:

![Bumpy 3D Prints](/images/MPCNC/print-artifacts.jpg "Top: SD Card Print; Bottom: Octoprint")

During these curves, I would notice my printer "stuttering" and moving extremely slowly over the area, which was uncharacteristic of the printer. I looked into this issue for a little bit - it turned out to be related to the way [Octoprint](https://octoprint.org/) interfaces with the 3D printer's mainboard in sending the serial data. I suppose the G-Code for the curves tend to overload the serial buffer thus the stuttering. This issue was solved by printing with the traditional method of using a microSD card straight into the mainboard.

After 240+ hours of printing (not including failed prints) I was ready to assemble. I had previously cut all of the steel conduit to length while waiting for the prints. First, I needed a table for this CNC to go on. I put together a simple and rigid work table from 2" x 4" lumber and a sheet of MDF on top to act as the work surface and spoilboard. Sheet goods (4' x 8') are always hard for me to acquire as I do not have a truck, and need to get them cut in half at my local home improvement store before they can fit in my car. I had the opportunity to use my new jobsite table saw to further size the sheets of MDF. Once mounted, I also partially cut two lines a few inches away from the edge, so the middle section is replaceable when it inevitably gets mangled, and I don't have to disassemble my CNC machine.

Here's the table with part of the CNC mounted:
![CNC Partial](/images/MPCNC/cnc-partial.jpeg "Table with beginning assembly")

There was a slight pause in the project as I had to return to college. More to come!

### Update Winter 2020-2021
It's finished! I certainly could've banged this out by the end of the summer, however I enjoyed taking my time with this build (and spending some much needed time with the friends and family I couldn't see during lock-down) as it has allowed me to think everything through in every step of the process.

CNC almost assembled! Just to mount the stepper motors, belts, pulleys, and wiring.
![CNC Assembly](/images/MPCNC/cnc-more.jpeg "CNC almost assembled!")

Some wire management, using a cheap tape measure to give some rigidity to the cable harness. For protection and a cleaner look, I wrapped all the wires in nylon cable sleeving. I also opted to use a different "spindle" than what was recommended from the plans - my Makita compact router is more powerful and has variable speed control, which makes my machine more robust.
![CNC Done](/images/MPCNC/cnc-wires.jpeg "CNC wiring, with tape measure trick")

The choice of firmware to run on the mainboard to control the CNC router was Marlin. While Marlin is not typically used for CNC machines (it's predominantly used for 3D printing), it has features that allow it to work, and I was familiar with it since it's the same firmware on my 3D printer. The other alternative was GRBL, which I may try in the future to see the features it has that Marlin does not. I pulled the latest bugfix version of Marlin from the official GitHub, and tweaked the configuration files. With my particular control board, the BTT SKR V1.4 Turbo, flashing firmware was as easy as compiling it onto a microSD card and then powering up the mainboard.

**Total Cost:** $600+

