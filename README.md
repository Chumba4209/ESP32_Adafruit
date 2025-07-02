# ESP32 BMP180 Adafruit IO Uploader with OLED & WiFiManager

This project uses an **ESP32**, **BMP180 barometric sensor**, and **OLED display** to:
- Read **temperature** and **pressure**
- Display the data on-screen
- Upload the values to **Adafruit IO** using MQTT
- Use **WiFiManager** for easy configuration of Wi-Fi and Adafruit IO credentials



##  Features

- 📡 Runtime setup of WiFi and Adafruit IO credentials using WiFiManager
- 🌡 Reads data from BMP180 sensor
- ☁ Sends data to Adafruit IO MQTT feeds
- 🖥 Displays sensor values on a 128x64 OLED
- 🔁 Uploads data every 5 seconds


##  Hardware Required

| Component           | Quantity |
|---------------------|----------|
| ESP32 Dev Board     | 1        |
| BMP180 Sensor       | 1        |
| OLED Display (128x64, SSD1306) | 1        |
| Breadboard + Jumper Wires | 1 set    |

###  ESP32 I2C Wiring

| Signal | GPIO |
|--------|------|
| SDA    | 23   |
| SCL    | 22   |

---

##  Libraries Used

Install the following libraries using the Arduino Library Manager:

- `Adafruit BMP085 Unified`
- `Adafruit GFX Library`
- `Adafruit SSD1306`
- `Adafruit MQTT Library`
- `WiFiManager by tzapu`



##  Setup Instructions

1. Flash the code to your ESP32 board.
2. Upon boot, ESP32 starts an access point called `BMP180_Config`.
3. Connect to the AP using your phone or computer.
4. Enter:
   - Wi-Fi SSID and password
   - **Adafruit IO Username**
   - **Adafruit IO Key** (from your [Adafruit IO dashboard](https://io.adafruit.com))
5. Click **Save**, and the ESP32 will reboot and connect automatically.



##  Adafruit IO Feeds

The device will publish to these feeds (automatically generated):

- `your_username/feeds/BMP_Temperature`
- `your_username/feeds/BMP_Pressure`

You can visualize the data on [Adafruit IO Dashboards](https://io.adafruit.com/dashboards).



##  OLED Display Output

![image](https://github.com/user-attachments/assets/d2c888fa-22a2-43c6-8b85-30b471d941fe)


---

##  Serial Monitor Output

![image](https://github.com/user-attachments/assets/86b16662-3185-4449-af69-7fe74c37be6b)




##  Notes

- WiFiManager starts every time on boot, for easier testing.
- You can modify the update frequency by changing the delay at the end of the `loop()`.
- The code uses Adafruit’s MQTT broker: `io.adafruit.com`, port `1883`.

---

##  Troubleshooting

-  **"Sensor Error"** on OLED: Check BMP180 wiring and I2C pins.
-  **"Failed to publish"**: Re-check Adafruit IO credentials or connection.
-  If config portal does not show, press the **EN/RST button** on the ESP32 and try again.







