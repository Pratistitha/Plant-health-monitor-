# 🌱 Plant Health Monitor

A simple Arduino-based system that tracks soil moisture, temperature, and humidity to help monitor plant health in real time.

## Overview

This project uses an Arduino Uno with a soil moisture sensor and a DHT11 temperature/humidity sensor to continuously monitor conditions around a plant. An LED gives a quick visual indicator of whether the soil is dry, and all readings are logged to the Serial Monitor.

## Components used

- Arduino Uno
- DHT11 temperature & humidity sensor
- Soil moisture sensor
- LED + resistor
- Breadboard + jumper wires

## Circuit diagram

*(insert your circuit diagram image here)*

**Connections:**
- DHT11: VCC → 5V, GND → GND, DATA → A3
- Soil moisture sensor: VCC → 5V, GND → GND, AOUT → A0
- LED: anode → resistor → pin 7, cathode → GND

## How it works

1. The DHT11 sensor reads ambient temperature and humidity.
2. The soil moisture sensor reads an analog value indicating how dry or wet the soil is.
3. If the soil moisture value exceeds a threshold (500), the LED turns on to indicate the soil is dry.
4. All readings (temperature, humidity, soil moisture, and status) are printed to the Serial Monitor every second.

## Setup / how to run

1. Wire the components according to the circuit diagram above.
2. Install the **DHT sensor library** in Arduino IDE (Sketch → Include Library → Manage Libraries → search "DHT sensor library" by Adafruit).
3. Upload `plant_monitor.ino` to your Arduino Uno.
4. Open the Serial Monitor (9600 baud) to view live readings.

## Next steps

- Add an LCD screen for standalone readouts without needing a computer/Serial Monitor
- Add data logging (e.g. to an SD card or cloud service) for tracking trends over time
- Add a buzzer or additional alert for critical dryness levels

## Author

Built by Pratistitha as a personal embedded systems project.
