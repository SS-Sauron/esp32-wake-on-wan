# Security Best Practices

- **Never commit credentials** – use a config file outside the repo
- **Use strong MQTT passwords** (≥16 random chars)
- **Keep ESP32 firmware up to date**
- **Consider a local MQTT broker** (Mosquitto) for full privacy
- **Rotate credentials periodically**
- **If you expose MQTT broker publicly, enable IP whitelisting** (available in paid HiveMQ plans)