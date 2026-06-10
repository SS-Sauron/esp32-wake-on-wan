# Setup Guide

## 1. Enable Wake-on-LAN on your PC

- Enter BIOS and enable "Wake on LAN" / "Power on by PCI‑E"
- In Windows: Device Manager → Network Adapter → Power Management → "Allow this device to wake the computer"
- Advanced tab: "Wake on Magic Packet" = Enabled

## 2. Flash the ESP32

- Install Arduino IDE + ESP32 board package (≥2.0.14)
- Install PubSubClient library
- Open `firmware/esp32_wol_relay.ino`
- Edit WiFi SSID/password, MQTT credentials, and target MAC address
- Upload

## 3. Set up HiveMQ Cloud

- Create free account at hivemq.com
- Create a Serverless cluster
- Under Access Management, add username/password
- Note the cluster URL (e.g., `abc123.s1.eu.hivemq.cloud`)

## 4. Install the wake script on your remote machine

- `sudo apt install mosquitto-clients`
- Copy `scripts/wake_my_pc.sh` and `config/wake_my_pc.conf.example` to `~/.wake_my_pc.conf`
- Edit the config file with your HiveMQ credentials
- Run `./wake_my_pc.sh`

## 5. Test

- Put your PC to sleep
- From remote machine, run `./wake_my_pc.sh`
- PC should power on within 60 seconds