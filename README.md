# 🔥 IoT Smoke Detector using ESP8266 + MQ-2 + Blynk

## 📌 Overview

This project is an **IoT-based Smoke Detector** built using **ESP8266 (NodeMCU), MQ-2 Smoke Sensor, and Blynk App**.
The system continuously monitors smoke levels and sends **real-time values** to the Blynk app.

If the smoke concentration exceeds a threshold, the system:

* Sends a **push notification (alert)** to the user.
* Displays sensor readings on the Blynk dashboard.

This project is a great example of **IoT + Embedded Systems + Cloud Integration** for **safety and monitoring applications**.

---

## 🛠️ Components Used

* ESP8266 NodeMCU (or ESP-01 with breakout board)
* MQ-2 Smoke & Gas Sensor
* Blynk App (Android/iOS)
* WiFi Network
* Jumper Wires + Breadboard

---

## ⚡ Circuit Connections

| Component        | ESP8266 Pin |
| ---------------- | ----------- |
| MQ-2 Sensor (AO) | A0          |
| VCC              | 3.3V        |
| GND              | GND         |

> Note: Use **3.3V power supply** for ESP8266. If MQ-2 requires **5V**, power its VCC with 5V but connect **AO to A0** safely (ESP8266 analog pin supports max **1V**, so use a **voltage divider**).

---

## 📜 Code Explanation

* **Libraries Used**

  * `ESP8266WiFi.h` → for WiFi connection
  * `BlynkSimpleEsp8266.h` → Blynk IoT communication
  * `SimpleTimer.h` → periodic data sending

* **Authentication & WiFi**

  * Insert your **Blynk Auth Token**
  * Enter **WiFi SSID & Password**

* **Working**

  * MQ-2 sensor gives **analog value** depending on smoke/gas concentration.
  * ESP8266 reads this value and sends it to **Blynk Virtual Pin V2**.
  * If the value exceeds **140**, an **alert notification** is triggered.

---

## 📊 Example Blynk Output

* **Real-time sensor graph** on Virtual Pin V2
* If smoke detected (value > 140):

  ```
  🔔 Notification: Smoke Detected!
  ```

---

## 🚀 How to Run

1. Install **Blynk app** on your phone.
2. Create a new project → Select **ESP8266** → Get **Auth Token** from email.
3. Add a **Value Display / Gauge / Graph widget** linked to **V2**.
4. Add **Notification widget**.
5. Connect MQ-2 to ESP8266 as per circuit.
6. Update the code with **Auth Token, WiFi SSID, and Password**.
7. Upload code using Arduino IDE.
8. Open Blynk app → view live smoke readings and alerts.

---

## 📂 Repository Structure

```
📁 IoT-Smoke-Detector
 ┣ 📜 SmokeDetector.ino       # Arduino Source Code
 ┣ 📜 README.md               # Documentation (this file)
 ┣ 📁 images/                 # Circuit diagram, Blynk screenshots
 ┣ 📜 LICENSE                 # (Optional) Open-source license
```

---

## 🎯 Applications

* Home safety & fire alarm system
* Industrial smoke monitoring
* Smart building IoT safety integration
* Kitchen smoke detection

---

## 📌 Future Improvements

* Add **buzzer + LED alarm** for local alert.
* Send **Email/SMS alerts** using Blynk/IFTTT.
* Integrate with **Firebase / MQTT** for data logging.
* Use multiple gas sensors (MQ-135, MQ-7) for CO₂/CO detection.

---

## 📜 License

This project is open-source under the **MIT License**.
Feel free to use and modify for learning and academic purposes.

---
