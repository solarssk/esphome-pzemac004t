# ESPHome + PZEM-004T (v3)

This project provides an ESPHome configuration for monitoring electrical parameters using the PZEM-004T (v3) module and an ESP8266 (e.g., ESP-01). This setup allows for real-time tracking of energy consumption within a smart home environment.

## 📦 Hardware Requirements

- **ESP8266**: Such as the ESP module.
- **PZEM-004T v3**: Single-phase energy meter for measuring voltage, current, power, and energy.
- **Home Assistant**: With ESPHome integration for seamless monitoring and control.

## 🔌 Wiring Instructions

**Important**: Ensure all wiring is performed with the power turned off to prevent electrical hazards.

1. **Power Connections**:
   - Connect the `5V` pin on the PZEM-004T to the `5V` pin on the ESP8266.
   - Connect the `GND` pin on the PZEM-004T to the `GND` pin on the ESP8266.

2. **UART Communication**:
   - Connect the `TX` pin on the PZEM-004T to the `RX` pin on the ESP8266.
   - Connect the `RX` pin on the PZEM-004T to the `TX` pin on the ESP8266.

3. **Energy Measurement**:
   - For the 100A version of the PZEM-004T, attach the external current transformer (CT) around the live wire of the circuit you wish to monitor. Ensure the orientation of the CT is correct, following the manufacturer's guidelines.

For detailed installation steps and safety precautions, refer to the comprehensive guide by Filip Chochół:  [Home Assistant: Measure electricity with PZEM004T](https://chochol.io/en/smart-home/home-assistant-measure-electricity-with-pzem004t/)

## 📁 Files in This Repository

- `pzmac004t.yaml`: Main ESPHome configuration file.
- `secrets.yaml` (not included): Contains your Wi-Fi credentials and other sensitive information.

## 🔐 Sample `secrets.yaml`

Create a `secrets.yaml` file in your ESPHome directory with the following content:

```yaml
wifi_ssid: "YourWiFiSSID"
wifi_password: "YourWiFiPassword"
```

## ⚙️ Configuration Overview
- **UART Interface**: Facilitates Modbus communication with the PZEM-004T.
- **Sensors Exposed**:
  - Voltage (V)
  - Current (A) ￼
  - Power (W) ￼
  - Energy (kWh)
  - Frequency (Hz)
  - Power Factor (%) ￼
- **Web Interface**: Enabled on port 80 for real-time monitoring.
- **OTA Updates**: Supports over-the-air updates for easy maintenance.
- **Home Assistant Integration**: Seamless integration via the native API.

## 🚀 Usage Instructions

1. **Flashing the Firmware**:
   - Use ESPHome to compile and upload the pzmac004t.yaml configuration to your ESP8266 device.

2. **Hardware Setup**:
   - Connect the PZEM-004T module to the ESP8266 as per the wiring instructions above.
   - Install the current transformer (if using the 100A version) around the live wire of the circuit to be monitored.

3. **Integration with Home Assistant**:
   - Once the ESP8266 is online and connected to your Wi-Fi network, Home Assistant should automatically detect the new ESPHome device.
   - Add the device through the Home Assistant interface to start monitoring the electrical parameters.
