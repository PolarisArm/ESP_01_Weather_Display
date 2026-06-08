# ESP01 Weather Display

A simple ESP8266-based temperature and humidity monitor using a DHT22 sensor and a 128×64 SSD1306 OLED display.

The project displays real-time temperature and humidity readings on a custom OLED dashboard.

## Features

* Reads temperature from a DHT22 sensor
* Reads relative humidity from a DHT22 sensor
* Displays values on a 128×64 SSD1306 OLED
* Custom bitmap background interface
* Updates measurements every second

## Hardware Required

* ESP-01S module
* DHT22T emperature & Humidity Sensor
* SSD1306 128×64 OLED Display (I²C)

## Wiring

### OLED Display (SSD1306 I²C)

| OLED Pin | ESP8266 Pin |
| -------- | ----------- |
| VCC      | 3.3V        |
| GND      | GND         |
| SDA      | GPIO0       |
| SCL      | GPIO2       |

The code initializes I²C using:

```cpp
Wire.begin(0, 2);
```

Where:

* GPIO0 = SDA
* GPIO2 = SCL

### DHT22 Sensor

| DHT22 Pin | ESP8266 Pin |
| --------- | ----------- |
| VCC       | 3.3V        |
| DATA      | GPIO1       |
| GND       | GND         |

The code uses:

```cpp
#define DHTPIN 1
#define DHTTYPE DHT22
```

## Libraries

Install the following PlatformIO libraries:

```ini
lib_deps =
    adafruit/Adafruit SSD1306
    adafruit/Adafruit GFX Library
    adafruit/DHT sensor library
```

## PlatformIO Example

```ini
[env:esp12e]
platform = espressif8266
board = esp12e
framework = arduino

lib_deps =
    adafruit/Adafruit SSD1306
    adafruit/Adafruit GFX Library
    adafruit/DHT sensor library
```

## Display Layout

The OLED displays:

* Temperature in the upper section
* Humidity in the lower section
* Custom bitmap background for visual styling

Values are refreshed once per second.



