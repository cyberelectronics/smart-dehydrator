# Smart Touch Dehydrator (ESPHome)

A custom, open-source firmware based on ESPHome to upgrade a standard food dehydrator into a smart, touch-controlled appliance with seamless Home Assistant integration. 

Powered by an ESP32-S3 microcontroller, this project replaces the original "dumb" electronics with a modern, interactive LVGL graphical interface and precise PID temperature control.

## ✨ Key Features

* **Interactive Touch Interface (LVGL):** A responsive, custom-designed UI on a 320x240 display. Easily adjust the target temperature, set the timer, and monitor real-time data directly on the device.
* **Precision PID Temperature Control:** Utilizes a BME280 sensor and slow PWM to perfectly maintain the target temperature (e.g., exactly 50°C) without the extreme fluctuations typical of cheap bi-metal thermostats.
* **Full Home Assistant Integration:** Automatically discovered via Home Assistant. Monitor current temperature, humidity, and remaining time, or start/stop the dehydration process remotely.
* **Advanced Safety System:** * **Thermal Runaway Protection:** Automatically cuts off heating and triggers an alarm if the temperature climbs uncontrollably.
  * **Sensor Failure Detection:** Shuts down the system safely if the BME280 sensor disconnects or fails.
  * **I2S Hardware Alarm:** Plays loud RTTTL warning sirens through an external DAC/speaker upon errors.
* **Smart Cool-Down Phase:** The fan automatically continues to run for a set period after the heating cycle ends to safely dissipate residual heat.
* **Autonomous Operation:** Fully functional offline. The built-in timers and logic ensure your food keeps drying safely even if the Wi-Fi drops or Home Assistant goes offline.
* **Captive Portal Setup:** Easy Wi-Fi configuration via a built-in access point mode (use a PC or a Laptop for WiFi config).

## 🛠️ Hardware Requirements

* **Board:** ESP32-S3-Touch-LCD-2.8 by Waveshare (display ST7789V (320x240) with CST328 Touch Controller and Speakers)
* **Sensors:** BME280 (Temperature, Humidity, Pressure) via I2C
* **Relays/Outputs:** Solid State Relays (SSR) for the heating element and for the fan
