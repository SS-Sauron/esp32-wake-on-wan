# Troubleshooting

## ESP32 does not connect to WiFi
- Verify SSID/password, use 2.4 GHz band only
- Check power supply (≥500mA)

## MQTT connection fails
- Confirm cluster URL, port 8883, username/password
- Ensure your firewall allows outbound TCP 8883
- For TLS errors, download the Let's Encrypt root CA

## PC does not wake up
- Double‑check MAC address in firmware
- Ensure WoL enabled in BIOS and OS
- Try sending Magic Packet from another device on the same LAN first
- Verify ESP32 serial shows `[WoL] Magic Packet broadcast`

## ESP32 crashes / reboots
- Check serial output for assertion failures
- Ensure `udp.begin()` is called **after** `WiFi.begin()` – our code does this.
- Increase watchdog timeout (default 20s is fine)