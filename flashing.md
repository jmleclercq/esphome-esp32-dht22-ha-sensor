# Flashing & Updates

## First flash (USB)
1. Connect ESP32 via USB
2. Run:

```bash
esphome run <your-yaml>.yaml
```

## OTA updates
Once the device is on Wi-Fi:

```bash
esphome run <your-yaml>.yaml
```

ESPHome will automatically select OTA if it can reach the device.

## Viewing logs
```bash
esphome logs <your-yaml>.yaml
```
