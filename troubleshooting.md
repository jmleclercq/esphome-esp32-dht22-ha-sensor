# Troubleshooting

## Sensor shows `nan` / no readings
- Check wiring: VCC/GND swapped is a classic.
- Try adding a 10k pull-up between VCC and DATA.
- Keep wires short (DHT sensors are sensitive to noise).

## ESPHome compiles but device never appears in Home Assistant
- Confirm Wi-Fi credentials in `secrets.yaml`.
- Check the device logs for IP address and API connection messages.
- Ensure Home Assistant ESPHome integration is installed and running.

## Frequent disconnects
- Ensure stable 3.3V power (avoid weak USB ports).
- Move ESP32 closer to Wi-Fi AP or add `wifi: output_power:` tuning.

## Wrong values
- DHT22 accuracy is limited; consider calibration or a higher quality sensor.
