# water-meter-measurement-system
This is an overview of different project part to digitalize an analog water meter and use it for a house automatization system to controll the water consumption.

**UPDATE: new Version for ESP32-CAM available on Thingiverse - much easyier and cheaper due to integrated camera and illumination
[https://www.thingiverse.com/thing:3860911](https://www.thingiverse.com/thing:3860911)**

## Overview

The system consists of a hardware fixture and and successiv software code to transform this finally to a measurement value for a database input.

<img src="./images/overview_ESP32-CAM.jpg">

To get an running system one needs 3 components:


| Component | 	Purpose  |	Link |
|:--------------:|:-------------|:--------|
| 1. Mechanical Fixture |	Hardware components to fix a camera and illumination on a water meter  | **[Version for ESP32-CAM](https://www.thingiverse.com/thing:3860911)**<br> [Version for ESP8266 + ArduCAM](https://www.thingiverse.com/thing:3238162)  |
| 2. Taking pictures |	ESP8266 based html server to provide pictures from the camera  | [https://github.com/jomjol/water-meter-picture-provider](https://github.com/jomjol/water-meter-picture-provider)  |
| 3. Server for data processing and evaluation |	Image processing (Cutting, OCR, ...) to extract the needed features  | [https://github.com/jomjol/water-meter-system-complete](https://github.com/jomjol/water-meter-system-complete) |

### The server is also as Docker-Container available for easy implementation:
* Server in **Docker-Container** [https://cloud.docker.com/u/jomjol/repository/docker/jomjol/wasserzaehler](https://cloud.docker.com/u/jomjol/repository/docker/jomjol/wasserzaehler)
* GitHub-Details on Server [https://github.com/jomjol/docker-wasserzaehler](https://github.com/jomjol/docker-wasserzaehler)

### Additional discussion with user experience
Extended user discussion can be found in the following forum: [https://forum.iobroker.net/topic/23577/wasserzähler-selfmade](https://forum.iobroker.net/topic/23577/wasserzähler-selfmade)

#### Details on image processing and signal chain within the server:

| Component | 	Usage  |	Link |
|:--------------:|:-------------|:--------|
| Alignment and decomposition |	Image processing with OpenCV library to extract the needed features  | [https://github.com/jomjol/water-meter-image-cut](https://github.com/jomjol/water-meter-image-cut) |
| OCR for full digits |	Usage for OCR to extract the m³ part of the water meter  | [https://github.com/jomjol/neural-network-digital-counter-readout](https://github.com/jomjol/neural-network-digital-counter-readout) |
| Analog to Digital Readout |	Usage of a Neural Network to digitalize analog pointers | [https://github.com/jomjol/neural-network-analog-needle-readout](https://github.com/jomjol/neural-network-analog-needle-readout) |
