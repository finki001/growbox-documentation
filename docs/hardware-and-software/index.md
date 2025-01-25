# Getting started
[Tasmota](https://tasmota.github.io/docs/) is used for controlling the lights fans etc. and for monitoring sensor data (via [MQTT](https://de.wikipedia.org/wiki/MQTT)) which is an open source
firmware for ESP based devices. I'm using an ESP32 but it does not really matter if you use an ESP866 for example -
most of the configurations are the same (apart from some minor details). It's documented quite well and also has a simple HTTP API if you prefer that over MQTT.1


(Re)set password via serial monitor and reboot device: `Backlog SSID1 [SSID]; Password1 [PASSWORD]; Restart 1`