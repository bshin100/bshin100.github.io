---
layout: post
title: LED Light Tiles
---

> TL;DR: Custom printed tiles using programmable WS2812B LEDs, inspired by nanoleaf.

Time frame: January 2019

![Finished product.](/images/moodlite.gif "Finished Product.")


This project is inspired by the triangular RGB LED light tiles commercially available by the company nanoleaf. A passionate maker was inspired by the same product, but was similarly not too stoked seeing the price. I decided to follow the open-source guide and design made available by this maker [called moodlite.](https://moodlite.co.uk/)

Essentially, these are highly customizable Wi-Fi enabled wall tiles that have programmable LEDs that diffuse through white 3D printed parts, and this brings a high-tech and colorful vibe to any room. There are limitless options in terms of integration, colors, and patterns.

I deviated from the main design in that I decided to place three LEDs per corner of the triangular tiles so that they would be brighter. I also initially opted to use a more powerful Arduino-based Wi-Fi chip, the ESP32 as opposed to the ESP8266. 

While 3D printing appears to be a matter of clicking a few buttons and having the machine spit out parts, there is much more to that, involving hundreds of hours of research that I may detail in a future post. The main difficulties in this 3D printing project involved bed adhesion for such a large surface area. While it seems counter-intuitive that a large surface area has trouble sticking to a print bed, the corners of these parts peeled up and caused warping of the print - in a project where a flat and clean prints are imperative to the final product. I also had to decide the color of my filament. There are many different brands and compositions, even in just PLA, so "white" isn't a simple choice. The brand of white I had diffused well, and I also tested clear filament at different infill levels to see the effect.

![Diffusion testing](/images/led-testing.gif "Diffusion testing")

The project involved a lot of careful planning and soldering between each strip of LEDs in each tile. The most challenging part (even to this day) is still the programming on the microcontroller. I couldn't manage to run even a basic test to drive the LEDs despite hours of research and combing through forums. I believe it had something to do with logic-level or timing, but even with a logic-level converter it still didn't work. The code base for this moodlite project is also open source  I wanted to just get the LEDs running so I currently run the tiles with a comparatively primitive Arduino Nano chip that is not Wi-Fi enabled. Earlier in 2020, I decided to give in and purchase an ESP8266 which is what the project was designed to run on, but upon an initial test, still no luck even on vanilla code. 

The next steps are to continue troubleshooting the WiFi chip and perhaps port IFTT protocols so the tiles can be controlled via voice assistants like the Amazon Alexa. Another idea if the open-source code doesn't work (or the chip) is to write custom code for the chip to receive commands and then transfer it through serial to the Arduino Nano, which will drive the LEDs.

Total cost of the project so far is about $80, including filament costs.



