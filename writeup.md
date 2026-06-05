# BLE Proximity Detection
## Alexander Wang 
## ECE 196 SP26
---

### Abstract

This tutorial will walk you through implementing **rough distance measurement using bluetooth RSSI strength signals**. It will also give a brief overview of how to use the ESP32's BLE features, how to lock on to a specific bluetooth signal, and how to filter the RSSI strength number for a more reliable signal. Finally, the tutorial will also go into additional supporting logic for our car autolocking project as an example of a possible use case. 

### Objectives
* [Introduction](#introduction)
    * [Theory](#theory---ece-101)
* [Supplies](#supplies)
* [Hardware](#hardware)
    * [Sub-feature A](#21-sub-feature-a)
    * [Sub-feature B](#22-sub-feature-b)
* [Conclusion](#3-conclusion)

---

### Introduction 

One problem that you may encounter while designing your device for a given problem is figuring out the distance between two different devices. If both of these devices support bluetooth, then the Bluetooth Low Energy (BLE) Received Signal Strength Indicator (RSSI) might be a straightforward solution to your problem. 

#### Limitations
Although BLE RSSI is a noisy signal, interfered with by many common materials, including people, which can cause readings to have wild variance, some signal smoothing techniques can mitigate these issues and provide a decent form of near vs. far detection.

#### Theory - ECE 101 (Basic Signal Filtering)

Assuming that the distance between the two bluetooth devices will not be changing very quickly, we know that a ground truth of distance should be a relatively slowly changing quantity, and thus the BLE RSSI should also reflect that quality.

Meanwhile, interference factors for the BLE RSSI signal will likely introduce a form of noise that may only briefly affect the signal, say for 1 or 2 readings. The readings themselves will also have a consistent fluctuation.

In the context of signal processing, this means that the quantity we care about is low frequency, while the signal that distorts our measurements is high frequency. Lets say the quantity we care about is a function $x(t)$, while the noise is captured by the function $c(t)$. 

Then, we can say that our measured signal $y(t)$ is the sum of both functions:

$$y(t)=x(t) +c(t)$$

### Supplies

For this tutorial, you will need an ESP32 Devboard, and a bluetooth device capable of advertising itself to other devices for discovery.

---

### Hardware

---

### Software

#### Estimating Distance via RSSI

#### Modelling Your Measured System for Kalman Filtering

#### Car Autolock Example: Modelling a Person Walking Away


