---
layout: post
title: Arduino Controlled Blinds
tags: [electronics, Arduino, programming, 3D printing]
description: An Arduino project which opens vertical blinds at sunrise and closes them at sunset.
---

<video style="width: 400px; max-width: 100%" autoplay loop>
  <source src="/assets/media/motorized-blinds/motorized_blinds.mp4" type="video/mp4">
</video>

### Overview

In my previous apartment, I had vertical blinds covering a sliding glass door that I liked to have open during the day and closed at night. Rather than spend 30 seconds each day opening and closing them, I decided to spend 2 months automating it 😁.

The project involved designing and building a mount for attaching an Arduino-controlled stepper motor to the blinds. 

### Parts of a Vertical Blinds System

To understand how this project works, it helps to understand a few key parts of a vertical blinds system.

![headrail]({{ "/assets/media/motorized-blinds/headrail_end.jpg" | absolute_url }}){: width="400px"}

In the above picture, you see the *headrail* with its end cap removed. The metal rod pointing towards the camera and running the length of the headrail is called the *pinion rod*. Down the pinion rod you see the *wand* hanging from the *tilt control*. When you turn the wand with your hands, the tilt control turns the pinion rod, which rotates the vertical blinds hanging from the pinion rod. This is called *tilting* the blinds.

The stepper motor is mounted directly to the pinion rod so that it can tilt the blinds open and closed.

### Tilt Control

The original tilt control contains a gearbox for creating mechanical advantage between the wand and the pinion rod. This makes tilting the blinds using the wand effortless, but if you try to turn the pinion rod directly you end up fighting the gearbox.

In order for a motor to be able to turn the pinion rod, the original tilt control needed to be replaced. I couldn't just remove the tilt control because the blinds cover a sliding glass door, and I still needed to be able to use the wand to slide the blinds open. Instead I created a new tilt control which doesn't interfere with the rotation of the pinion rod.

The new tilt control which has the same dimensions as the old tilt control, but has no gearing and allows the pinion rod to spin freely.

![tilt control 2]({{ "/assets/media/motorized-blinds/tilt_control_2.jpg" | absolute_url }}){: width="400px"}

![tilt control 3]({{ "/assets/media/motorized-blinds/tilt_control_3.jpg" | absolute_url }}){: width="400px"}

![tilt control 1]({{ "/assets/media/motorized-blinds/tilt_control_1.jpg" | absolute_url }}){: height="400px"}

The white plastic part bolted to the new tilt control is the tilt mechanism for the first vertical blind. Each vertical blind is connected to the headrail via a tilt mechanism. The tilt mechanisms convert rotation of the pinion rod into rotation of the blinds.

When you use the wand to slide the tilt control along the headrail, the tilt control pulls the first blind, which pulls the second blind, which pulls the third, etc. along the rail.

![installed tilt control]({{ "/assets/media/motorized-blinds/tilt_control_installed.jpg" | absolute_url }}){: width="400px"}

### The Motor Assembly

The collection of 3D printed pieces for linking the motor to the pinion rod, mounting the circuit board, and securing everything to the headrail is what I'm calling the "Motor Assembly". The Motor Assembly was designed with a couple goals in mind:

1. Provide a way to link the motor to the pinion rod
1. Use gears to assist the motor in turning the pinion rod
1. Mount to the headrail using its existing screw holes (no permanent modifications)
1. Do so in a compact manner

Here's what I came up with

![annotated motor assembly]({{ "/assets/media/motorized-blinds/annotated_motor_assembly.jpg" | absolute_url }}){: width="600px"}

* A - stepper motor
* B - structural plate
* C - 16 tooth gear - connects directly to the stepper motor
* D - PCB standoff
* E - back plate - keeps the gears in place and provides a surface for mounting the PCB
* F - 24 tooth gear - connects directly to the pinion rod
* G - headrail mount - goes inside the headrail and secures the entire assembly to the headrail

![motor assembly rotated]({{ "/assets/media/motorized-blinds/motor_assembly_rotated.jpg" | absolute_url }}){: width="400px"}

![motor assembly back]({{ "/assets/media/motorized-blinds/motor_assembly_back.jpg" | absolute_url }}){: width="400px"}

### Electronics

#### Circuit Board

The circuit board has two integrated circuits: an ATtiny84 running Arduino and an SN754410 motor driver. Power is provided via a 12v power supply connected to a DC power jack. The stepper motor is connected to supply voltage while the ICs are connected to the output of a 5v linear voltage regulator.

![pcb top]({{ "/assets/media/motorized-blinds/pcb_top.jpg" | absolute_url }}){: width="400px"}

![pcb bottom]({{ "/assets/media/motorized-blinds/pcb_bottom.jpg" | absolute_url }}){: width="400px"}\\
*Messy, but it works*

#### Photoresistor

A photoresistor is used to sense the ambient light level outside. The blinds are toggled open or closed when the light level crosses a predetermined threshold and remains on that side of the threshold for at least 3 minutes. Requiring that the light level stay on one side of the threshold for at least 3 minutes prevents the blinds from oscillating when the light level hovers around the threshold.

![photoresistor]({{ "/assets/media/motorized-blinds/photoresistor.jpg" | absolute_url }}){: width="400px"}

#### Button

The button hangs down from the motor and lets me manually toggle the tilt of the blinds. It's just a push button soldered to a 2-conductor wire and glued inside a 3D printed enclosure. The blinds will toggle when the button is pressed, regardless of the light level outside.

![push button 1]({{ "/assets/media/motorized-blinds/push_button_1.jpg" | absolute_url }}){: width="400px"}

![push button 2]({{ "/assets/media/motorized-blinds/push_button_2.jpg" | absolute_url }}){: width="400px"}

### Installation

This is the final result with everything installed

![installation 1]({{ "/assets/media/motorized-blinds/installation_1.jpg" | absolute_url }}){: width="400px"}

![installation 2]({{ "/assets/media/motorized-blinds/installation_2.jpg" | absolute_url }}){: width="400px"}

![installation 3]({{ "/assets/media/motorized-blinds/installation_3.jpg" | absolute_url }}){: width="400px"}
