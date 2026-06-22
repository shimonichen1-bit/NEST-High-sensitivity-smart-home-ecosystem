# NEST: Smart Home & Security System

An Arduino-based IoT project combining passive environmental monitoring with an active home security system. 

## Features

* **Live Monitoring:** Tracks room temperature, humidity, light, and noise levels in real-time.
* **Two-Stage Hazard Escalation:** Senses ambient smoke, but escalates to a high-priority Fire Alert only if the local temperature exceeds 45°C.
* **Intruder Detection:** Uses a PIR motion sensor to secure the premises when armed.
* **Cloud Sync:** Streams raw and processed telemetry to a live ThingSpeak dashboard.
* **Local Display:** Outputs current system status directly to an I2C LCD screen.

## System Controls

The system state is managed via a single push-button interface:

* **2 Presses:** Arms the system (enables motion detection).
* **3 Presses:** Disarms the system (returns to passive monitoring).
* **1 Press (while armed):** Triggers a tamper warning, logged as an unauthorized attempt.

## Hardware Components

* Arduino Uno
* ESP8266 WiFi Module
* I2C LCD Display
* Sensors: DHT11 (Temp/Humidity), BH1750 (Light), HC-SR501 (Motion), Keyestudio KS0036 (Smoke), Keyestudio KS0035 (Sound)

## Setup

1. Assemble the hardware according to the project schematics.
2. Create a `secrets.h` file in the root code directory:
```cpp
   #define SECRET_SSID "Your_WiFi_Name"
   #define SECRET_PASS "Your_WiFi_Password"
