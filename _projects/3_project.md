---
layout: page
title: Industrial Anomaly Detection
description: Anomaly Detection in Industrial Environments for Disaster Prevention
img: assets/img/capstone.png
importance: 3
category: research
---

In large industrial setting, system failure can cost big sums of money and in the worst case, loss of human lives. However, it is inevitable that industrial equipment degrades with time, making it hard to predict when a system failure will happen. Usually, devices change their characteristic sounds when they degrade, but humans cannot monitor these changes without the help from a digital system. Therefore, we presented a Convolutional Neural Network (CNN) model to detect anomalies in an industrial environment.

We used a large-scale public industrial audio dataset as input, which contains audio files of equipment like fan, valve, pump, and slider. I preprocessed the audio files using noise cancellation algorithms (RNNoise an BRIL) or digital signal processing filters. Next, we made spectrograms of the audio inputs and fed them into Conoolutional Neural Network (CNN) model. To optimize the accuracy of the CNN model, I researched data augmentation since the imbalanced dataset has less abnormal data (which is typical in real settings) and performed augmentation using SMOTE. The accuracy of our final 2D CNN model was 97%, averaging on different equipment.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/system1.png" title="CNN model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/system2.png" title="Inference" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/system3.png" title="On-device ML" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    System Diagram (Note: since the project was sponsored by Microchip, so we used VectorBlox SDK and Icicle Kit from Microchip)
</div>

We performed inference using our model and an Icicle Development Kit. The Icicle Kit contains an FPGA which is programmed with the VectorBlox IP. VectorBlox IP is Microchip’s hardware block that performs inference on the board with our CNN model. And we tested the performance in reality by using the audio data collected from a demo fan. The accuracy reached 98%.

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

The overall performance of our selected model is very satisfactory. It produces excellent results when the SNR is -7dB or better (F-Measure > 0.90). In addition VectorBlox was found to produce good results with high performance (28ms/inference) with minimal impact from quantization.
