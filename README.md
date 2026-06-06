# ESP32 Security Research Tools

![ESP32](https://img.shields.io/badge/ESP32-C%2B%2B-E7352C?style=flat-square&logo=espressif&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-C%2B%2B-00979D?style=flat-square&logo=arduino&logoColor=white)
![License](https://img.shields.io/badge/use-research%20%2F%20educational-yellow?style=flat-square)

> Custom ESP32 firmware builds and Arduino sketches for WiFi/RF security research and network analysis.

---

## Overview

A collection of custom builds, modifications, and standalone tools built on ESP32 and Arduino platforms for security research, RF analysis, and network scanning. All tools are for **authorised testing and educational use only**.

---

## Projects in this repo

### 1. ESP32 Marauder — Custom Build

A custom fork and build of [ESP32 Marauder by justcallmekoko](https://github.com/justcallmekoko/ESP32Marauder) with modifications for personal use:

- Added custom serial commands for targeted beacon scanning
- Extended the evil-portal module with a captive portal template engine
- Custom housing design (3D-printed) for a compact, battery-powered probe
- Integrated SSD1306 OLED status display

**Hardware used:**
- ESP32 WROOM-32
- SD card module
- SSD1306 OLED
- 3.7V LiPo + TP4056 charger
- 3D-printed enclosure

**Build instructions** in `marauder-build/README.md`.

---

### 2. NRF24L01 Packet Sniffer

A standalone Arduino Mega + NRF24L01 sketch for monitoring 2.4 GHz band activity across all 125 channels. Inspired by the BTLEJuice approach but adapted for raw NRF24L01 promiscuous mode.

**Features:**
- Hop across all 125 channels, log RSSI + address fragments
- Identify channel congestion patterns
- Serial output compatible with GNU Radio for further analysis

---

### 3. WiFi Deauth Probe (Educational)

ESP32 sketch demonstrating the 802.11 deauthentication frame vulnerability (pre-802.11w). Sends targeted deauth frames to a specified BSSID.

> For use only on networks you own or have explicit written permission to test. This vulnerability is patched in WPA3/802.11w networks.

---

### 4. BLE Scanner

ESP32 BLE scanner that logs all nearby BLE advertisements (MAC, RSSI, device name, manufacturer data) to serial + optional Firebase log. Useful for mapping BLE device density in an area.

---

## Build & Flash

```bash
git clone https://github.com/kavinjainn/esp32-security-tools

# Each project has its own folder with a platformio.ini
cd marauder-build/
pio run --target upload

# Or: open the .ino in each folder with Arduino IDE
# Required board: esp32 by Espressif (v2.x)
```

---

## Legal / Ethical Use

These tools are for:
- Security research on networks/devices you own
- CTF competitions
- Educational understanding of WiFi/RF protocols
- Authorised penetration testing with written permission

**Do not** use for unauthorised access to networks or devices. WiFi deauthentication against networks you don't own is illegal in most jurisdictions.

---

## References

- [ESP32 Marauder](https://github.com/justcallmekoko/ESP32Marauder) by justcallmekoko
- [ESP32 Arduino Core](https://github.com/espressif/arduino-esp32)
- [RF24 Library](https://github.com/nRF24/RF24)

---

## About

Built by [Kavin Jain](https://kavinjain.in) for learning and research.
