# Hardware — SmartWaterQualityMonitoringSystem

## Parts and electrical limits
ESP32 DevKit and 3.3 V-safe analog turbidity module; 3.3 V-safe analog pH interface. Power low-voltage modules from a suitable regulated supply, tie grounds together, and verify signal levels before connection. GPIO34 is input-only and ADC1 is used because ADC2 conflicts with Wi-Fi. Never apply more than 3.3 V to an ESP32 GPIO.

| ESP32 pin | Connection | Requirement |
|---|---|---|
| ESP32 3V3 | sensor VCC | Verify module supply rating |
| ESP32 GND | sensor GND | Common low-voltage ground |
| GPIO34 (ADC1) | analog signal | Never exceed 3.3 V |
| GPIO35 (ADC1) | second analog signal | Never exceed 3.3 V |

Use a pull-down on GPIO14's driver input so the load remains off during boot. Low-voltage relays must not be connected directly to GPIO, and inductive loads need flyback protection.

## Sensor specification and calibration
The firmware accepts turbidity sensor signal from 0 to 4095 ADC counts. Secondary value is pH module signal (ADC counts). Raw sensor trends are not NTU, calibrated pH, or proof of potability; lab analysis is required. Use a multimeter and the sensor data sheet for the exact module revision.
