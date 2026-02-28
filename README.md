# ESPHome ESP32 DHT22 Sensor for Home Assistant

![ESPHome](https://img.shields.io/badge/ESPHome-Ready-3DDC84)
![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Integration-41BDF5)
![Platform](https://img.shields.io/badge/Platform-ESP32-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

A **100% local** temperature & humidity sensor for **Home Assistant**, built with an **ESP32** and a **DHT22/AM2302** using **ESPHome**.

> This repository is a clean, “production-style” version of my working setup.
> It focuses on reproducibility, clear wiring, and a minimal YAML you can adapt quickly.

---

## Features

- ✅ Temperature + humidity (DHT22)
- ✅ Native Home Assistant integration via ESPHome
- ✅ OTA updates
- ✅ No cloud dependency
- ✅ Optional static IP
- ✅ Secrets-based configuration (`secrets.yaml`)

---

## Hardware

- ESP32 dev board (ESP32 DevKit / ESP32-WROOM)
- DHT22 (AM2302) sensor
- Dupont wires
- *(Recommended)* 10k pull-up resistor between **VCC** and **DATA** (often already present on breakout boards)

See: **docs/hardware.md** and the wiring diagram: **docs/images/wiring.png**.

---

## Wiring (default)

| DHT22 pin | ESP32 |
|---|---|
| VCC | 3.3V |
| GND | GND |
| DATA | GPIO4 |

> GPIO4 is a safe default and matches this repo’s YAML.
> If you change the pin, update the YAML accordingly.

---

## Quick start

### 1) Install ESPHome

If you run Home Assistant OS/Supervised, ESPHome add-on is the easiest.

For CLI (Python):

```bash
python3 -m pip install --upgrade esphome
esphome version
```

### 2) Copy files

- Put `config/example-dht22.yaml` into your ESPHome folder (rename as you want, e.g. `livingroom-dht22.yaml`)
- Add required values to your `secrets.yaml`

Example `secrets.yaml` entries:

```yaml
wifi_ssid: "YOUR_WIFI_SSID"
wifi_password: "YOUR_WIFI_PASSWORD"
ota_password: "CHANGE_ME"
api_encryption_key: "BASE64_KEY_FROM_ESPHOME"
```

### 3) Flash (first time via USB)

```bash
esphome run livingroom-dht22.yaml
```

After the first flash, updates can be done OTA.

### 4) Add to Home Assistant

In Home Assistant: **Settings → Devices & services → ESPHome**
Your device should appear automatically.

---

## Documentation

- Configuration: **docs/configuration.md**
- Flashing & OTA: **docs/flashing.md**
- Troubleshooting: **docs/troubleshooting.md**
- Hardware & wiring: **docs/hardware.md**

---

## Roadmap

See **ROADMAP.md**.

---

## License

MIT © jmleclercq — see **LICENSE**.
