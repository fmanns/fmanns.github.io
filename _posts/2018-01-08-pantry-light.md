---
layout: post
title: Automatic Pantry Light
tags: [electronics, 3D printing]
description: LED light that turns on when I open my pantry door.
---

![finished 1]({{ "/assets/media/pantry-light/final.jpg" | absolute_url }}){: width="400px"}

### Overview

I wanted a light for my pantry. Specifically I wanted a light that would turn on and off automatically and wouldn't use any power when the door was closed. I couldn't find any products that matched exactly what I was looking for, so I made my own.

The light I built is a 30cm long, battery-powered LED strip. The LED strip and battery pack are attached to a 1x2 that hangs from the moulding on the inside of the pantry. A limit switch mounted just inside the doorframe turns the light on when the door opens.

### Switch

The switch is a micro limit switch mounted inside a 3D printed enclosure. The switch is connected to the light through a 3.5mm headphone jack, allowing the switch and light bar to be easily disconnected.

![switch 1]({{ "/assets/media/pantry-light/switch_1.jpg" | absolute_url }}){: width="400px"}\\
*3.5mm audio cable soldered to the switch*

The switch is wired in the [normally closed](https://en.wikipedia.org/wiki/Switch#Contact_terminology) configuration so that the light will be ON unless the door is pushed against the switch.

![switch 2]({{ "/assets/media/pantry-light/switch_2.jpg" | absolute_url }}){: width="400px"}\\
*Switch seated in its housing*
<br><br>

![switch 3]({{ "/assets/media/pantry-light/switch_3.jpg" | absolute_url }}){: width="400px"}\\
*Hot glue keeps the switch in place and alleviates cable strain*
<br><br>

![switch installed]({{ "/assets/media/pantry-light/switch_installed.jpg" | absolute_url }}){: width="400px"}\\
*Switch mounted inside the door frame*

### Circuit

As previously mentioned, the switch and light are wired through a 3.5mm headphone jack. The battery pack is soldered to the right channel of the headphone jack and the light is soldered to the left channel. When the switch closes, it connects the two channels and the light illuminates.

![circuit soldered]({{ "/assets/media/pantry-light/pcb_soldered.jpg" | absolute_url }}){: width="400px"}

![circuit glued]({{ "/assets/media/pantry-light/pcb_installed.jpg" | absolute_url }}){: width="400px"}\\
*Circuit glued into its housing*
<br><br>

![finished circuit]({{ "/assets/media/pantry-light/finished_circuit.jpg" | absolute_url }}){: width="400px"}\\
*Circuit completed and screwed to the 1x2*
<br><br>

![finished 2]({{ "/assets/media/pantry-light/finished_1.jpg" | absolute_url }}){: width="400px"}

The finished light. It hangs from the brackets mounted on each end, and the clips in the center hold the battery pack in place.
