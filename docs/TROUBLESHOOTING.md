# Troubleshooting — SmartWaterQualityMonitoringSystem

| Symptom | Check |
|---|---|
| No turbidity sensor signal | Verify sensor power, grounds, pin table, voltage limits, and module orientation. |
| Invalid sample | Check 0–4095 ADC counts range and sensor calibration. |
| Wi-Fi disconnected | Check SSID, 2.4 GHz coverage, and local network policy. |
| MQTT disconnected | Check broker DNS, port 8883, CA PEM, device credentials, and publish ACL. |
| Unexpected alert | Inspect raw turbidity sensor signal and pH module signal; calibrate the threshold in `logic.h`. |
| Build failure | Confirm PlatformIO is installed and dependency downloads are permitted. |

Raw sensor trends are not NTU, calibrated pH, or proof of potability; lab analysis is required.
