---
layout: page
title: Smart Earring
description: Self-Powered Earring for longitudinal Temperature Sensing
img: assets/img/earring.png
importance: 1
category: research
---

As body temperature is an important vital sign, it can be used as an indicator of physical wellbeing. Measuring body temperature has become more important during the pandemic. Moreover, studies showed that temperature is also associated with emotional states.
Longitudinal body temperature tracking would enable a better understanding of both physical and mental health.
Therefore, I led the design of a low-power, small-scale earring that can passively sense skin temperature on the earlobe on the earlobe and stream the data to mobile devices wirelessly.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Earring_2.png" title="smart earring" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Smart earring that sense skin temperature in natural daily scenarios, like in a meeting or during exercising, and stream the data to smartphone 
</div>

Considering the constraints of scale, weight, and power consumption of the earring, I explored different temperature sensors, Bluetooth modules, and coin cell batteries to achieve the optimized design. 
The final millimeter-scale system I designed and prototyped successfully receives accurate temperature data and streams to smartphones with microwatt-level power consumption.
See the picture of system design and first prototype below:

<div class="row">
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.html path="assets/img/demo.jpg" title="system design" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/prototype.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our system design contains two temperature sensors, a bluetooth module and a coin cell battery.
</div>

Now, I am actively exploring power harvesting techniques for wearables, including from kinetic and ambient energy sources such as daily activities and light, in order to enable self-powered longitudinal body temperature sensing without increasing the user burden.

The goal of this project is to achieve longitudinal body temperature tracking with a self-powered earring. With the longitudinal temperature data, we would apply machine learning to make further personalized inferences, including fever detection, menstrual cycle prediction, and potentially study the relationship between emotion and body temperature.
