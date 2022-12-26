---
layout: page
title: Industrial Anomaly Detection
description: Anomaly Detection in Industrial Environments for Disaster Prevention
img: assets/img/capstone.png
importance: 3
category: research
---

In large industrial setting, system failure can cost big sums of money and in the worst case, loss of human lives. However, it is inevitable that industrial equipment degrades with time, making it hard to predict when a system failure will happen. Usually, devices change their characteristic sounds when they degrade, an intelligent embedded system can help people notice or monitor these changes. Therefore, we presented a on-device Convolutional Neural Network (CNN) model to detect anomalies in an industrial environment.

We used a large-scale public industrial [audio dataset](https://zenodo.org/record/3384388#.Y6lTJOzMJQI) as input, which contains audio files recorded from four types of industrial machines, fans, valves, pumps, and slider rails. I first preprocessed the audio files using noise cancellation algorithms (RNNoise an BRIL) and digital signal processing filters. Next, we made spectrograms of the audio inputs and fed them into a 2D CNN model that we developed. To optimize the accuracy of the CNN model, I researched data augmentation since the imbalanced dataset has less abnormal data than normal data (which is typical in real settings) and performed augmentation using SMOTE. The accuracy of our final 2D CNN model was 97%, averaging on different equipment.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/system1.png" title="CNN model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/system2.png" title="Inference" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    System Diagram (Note: since the project was sponsored by Microchip, we used VectorBlox SDK and Icicle Kit from Microchip)
</div>

<div class="container">
    <div class="row">
        <div class="col-sm mt-4 mt-md-0">
            {% include figure.html path="assets/img/system3.png" title="On-device ML" class="img-fluid rounded z-depth-1" %}
        </div>
        <div class="col-sm mt-4 mt-md-0">
            {% include figure.html path="assets/img/polarfire.png" title="Icicle Kit" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    On-device anamaly detection with Microchip PolarFire® SoC FPGA Icicle Kit
</div>

We performed inference using our model and VectorBlox SDK. The [Icicle Kit](https://www.mouser.com/new/microchip/microchip-polarfire-soc-icicle-kit/?gclid=CjwKCAiAqaWdBhAvEiwAGAQltgHMAxjvTdjj_S1dXS-3dlGtuJpstzGBAw-_nAFeV1tDXc3GRd2UOBoC6UQQAvD_BwE) contains an FPGA which is programmed with the VectorBlox IP. VectorBlox IP is Microchip’s hardware block that performs inference on the board with our CNN model. And we tested the performance in reality by using the audio data collected from a demo fan. The accuracy reached 98%.

<div class="container">
    <div class="row">
        <div class="col-sm mt-3 mt-md-0">
            {% include figure.html path="assets/img/result.png" title="result" class="img-fluid rounded z-depth-1" %}
        </div>
    </div>
</div>
<div class="caption">
    Result from both Tensorflow model and VectorBlox IP Simulator
</div>

The overall performance of our selected model is very satisfactory. It produces excellent results when the SNR is -7dB or better (F-Measure > 0.90). In addition, VectorBlox was found to produce good results with high performance (28ms/inference) with minimal impact from quantization.
