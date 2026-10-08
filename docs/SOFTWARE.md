# Software — SmartWaterQualityMonitoringSystem

Firmware is C++ with Arduino on ESP32. `src/main.cpp` implements dual_analog acquisition, bounded JSON telemetry, Wi-Fi reconnection, TLS broker connection, and alert publication. `include/logic.h` defines value validation and the `turbidity sensor signal > 2600.0f || pH module signal < 900.0f || pH module signal > 3200.0f` rule. PlatformIO pins `platformio/espressif32@6.10.0` and `knolleary/PubSubClient@2.8.0`.

No backend, frontend, or database is part of this firmware-only architecture. An operator-supplied MQTT broker enforces the device's publish ACL and TLS identity. No watchdog API is configured; a hardware watchdog and persistent configuration are future work.
