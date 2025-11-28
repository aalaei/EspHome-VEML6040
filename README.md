# ESPHome VEML6040 Component

This is a custom component for [ESPHome](https://esphome.io) that supports the **Vishay VEML6040 RGBW Color Sensor**.

The VEML6040 is a high-accuracy color sensor that measures Red, Green, Blue, and White light intensity. This component exposes the raw channel values and calculates Illuminance (Lux) and Correlated Color Temperature (CCT).

## Features

* **RGBW Channels**: Reads raw 16-bit values for Red, Green, Blue, and White channels.
* **Illuminance (Lux)**: Calculates ambient light intensity based on the Green channel.
* **Color Temperature (CCT)**: Calculates the color temperature in Kelvin using the RGB inputs.
* **Configurable Integration Time**: Adjust sensitivity and measurement speed.

## Hardware Support

Supported hardware includes any ESP32, ESP8266, or RP2040 board with an I2C bus and a VEML6040 breakout board.

**Wiring Connection:**

| VEML6040 Pin | ESP Board Pin | Notes |
| :--- | :--- | :--- |
| **VCC** | 3.3V | Do not connect to 5V unless your board has a regulator |
| **GND** | GND | Common ground |
| **SDA** | GPIO 21 (ESP32) / D2 (ESP8266) | Or any valid I2C SDA pin |
| **SCL** | GPIO 22 (ESP32) / D1 (ESP8266) | Or any valid I2C SCL pin |

## Installation

You can use this component directly from GitHub using the `external_components` feature in ESPHome. Add the following lines to your YAML configuration file:

```yaml
external_components:
  - source: github://aalaei/EspHome-VEML6040
    components: [ veml6040 ]