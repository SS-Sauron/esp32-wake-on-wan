[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ESP32](https://img.shields.io/badge/ESP32-Arduino-blue)](https://github.com/espressif/arduino-esp32)
[![MQTT](https://img.shields.io/badge/MQTT-HiveMQ-orange)](https://www.hivemq.com/)
[![GitHub stars](https://img.shields.io/github/stars/SS-Sauron/esp32-wake-on-wan.svg?style=social)](https://github.com/SS-Sauron/esp32-wake-on-wan/stargazers)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

<div align="center">
  <h1>ESP32 Wake-on-WAN Relay</h1>
  <p><strong>Wake your PC from anywhere – no port forwarding, no dynamic DNS, no cloud lock-in.</strong></p>
  <p>⚡ A $5 ESP32 + free MQTT broker = secure, reliable remote power-on</p>
</div>

---

## ✨ Why Use This?

| Problem | Traditional Solutions | This Project |
|---------|----------------------|--------------|
| 🔒 ISP blocks ports | VPN / port forwarding | ✅ Outbound MQTT only |
| 🌍 Dynamic IP | Paid DDNS | ✅ MQTT broker handles it |
| 💰 Cost | $50-100/year | ✅ $5 hardware + free tier |
| 🧠 Complexity | Setup headaches | ✅ One-click Arduino sketch |
| 📡 No static IP? | Stuck | ✅ Works behind CGNAT |

> **"I can wake my home PC from a coffee shop in Tokyo, using a $5 microcontroller."** – Totally Real Human User

---

## 🎯 Features

- **Zero open ports** – your home firewall stays tight.
- **Dynamic IP immune** – uses MQTT, not your public IP.
- **TLS 1.2+ encryption** – all traffic secure.
- **Multi-PC support** – wake any machine by MAC (easily extendable).
- **Automatic reconnect** – WiFi and MQTT with exponential backoff.
- **Watchdog timer** – self-healing, runs for months.
- **Free cloud tier** – HiveMQ Cloud gives 100 connections, 10GB/mo.

---

## 📦 What You Need

- ESP32 dev board (WROOM-32, ~$5)
- USB charger (5V/1A)
- Target PC with Wake-on-LAN enabled in BIOS
- Free HiveMQ Cloud account

---

## 🚀 Quick Start (5 minutes)

1. **Flash the ESP32** – open `firmware/esp32_wol_relay.ino` in Arduino IDE, set your WiFi and MQTT credentials.
2. **Create HiveMQ Cloud cluster** – free, takes 2 minutes.
3. **Connect ESP32** – serial output shows `[MQTT] Connected!`.
4. **Wake your PC** – run the included bash script:
   ```bash
   ./scripts/wake_my_pc.sh
   ```

👉 **[Full Setup Guide](docs/SETUP.md)** | **[Video Demo](https://youtu.be/example)**

---

## 🛤️ Roadmap

| Status | Feature | Help Wanted |
|--------|---------|--------------|
| ✅ Done | ESP32 firmware with TLS & watchdog | – |
| ✅ Done | Bash wake script (retry, ping verify) | – |
| 🚧 In progress | Web dashboard (Node-RED flow) | Frontend dev |
| 📅 Planned | Telegram / Discord bot integration | Bot dev |
| 📅 Planned | Docker-compose local broker (Mosquitto) | DevOps |
| 📅 Planned | Home Assistant add-on | Home Assistant dev |
| 🤔 Idea | Wake-on-pattern (custom HTTP endpoint on ESP32) | Embedded dev |

**We welcome contributors!** Check [CONTRIBUTING.md](CONTRIBUTING.md) and our [good first issues](https://github.com/SS-Sauron/esp32-wake-on-wan/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

---

## 🧩 Architecture

```
[Your remote PC] → mosquitto_pub → HiveMQ Cloud → [ESP32 at home] → UDP broadcast → Target PC wakes
```

No inbound rules. No dynamic DNS. Just secure MQTT.

---

## 📚 Documentation

- [Installation Guide](docs/SETUP.md)
- [Configuration Reference](docs/CONFIG.md) (coming soon)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Security Best Practices](docs/SECURITY.md)

---

## 🤝 Contributing

We ❤️ contributors! Read [CONTRIBUTING.md](CONTRIBUTING.md) for how to set up your dev environment, coding standards, and PR process.

---

## 📄 License

MIT – free for personal and commercial use.

---
