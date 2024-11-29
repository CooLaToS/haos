
# Setting Up Wi-Fi on Home Assistant OS (HAOS)

This guide explains how to set up Wi-Fi on Home Assistant OS (HAOS) during the initial configuration.

---

## Requirements
- A Raspberry Pi with Home Assistant OS installed.
- Keyboard, monitor, and HDMI connection for access to the Home Assistant CLI.

---

## Steps to Configure Wi-Fi

### 1. Access the Home Assistant CLI
Once the system boots, you will see the `ha >` prompt on the screen.

---

### 2. Get Network Interface Information
Run the following command to list network interfaces and identify the Wi-Fi interface (typically `wlan0`):
```bash
network info
```

---

### 3. Update Wi-Fi Configuration
Run the following command to connect to your Wi-Fi network:

```bash
ha network update wlan0 --ipv4-method auto --ipv6-method auto --wifi-auth wpa-psk --wifi-mode infrastructure --wifi-ssid <WIFI-SSID> --wifi-psk <WIFI-PASS>
```

Replace:
- `<WIFI-SSID>`: Your Wi-Fi network name.
- `<WIFI-PASS>`: Your Wi-Fi password.

Example:
```bash
ha network update wlan0 --ipv4-method auto --ipv6-method auto --wifi-auth wpa-psk --wifi-mode infrastructure --wifi-ssid MyHomeWiFi --wifi-psk SuperSecretPass123
```

---

### 4. Verify the Connection
After updating the configuration, verify that the Wi-Fi connection is active by running:
```bash
network info
```

Check for the `wlan0` interface and ensure it's connected to the specified Wi-Fi network.

---

## Troubleshooting
- **No Wi-Fi interface:** Ensure your Raspberry Pi has a built-in Wi-Fi adapter or a compatible external adapter.
- **Incorrect credentials:** Double-check the Wi-Fi SSID and password.
- **Network issues:** Ensure the Wi-Fi network is in range and functional.

