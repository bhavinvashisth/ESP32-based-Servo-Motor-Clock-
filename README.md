# ⏰ ESP32 Based Servo Motor Clock

A unique and visually engaging **mechanical digital clock** built using **ESP32** and **28 servo motors**. Each segment of the digital display is controlled by servo motors, creating a futuristic flip-style time display.

---

## 📌 Project Overview

This project demonstrates a **servo-driven digital clock** where each digit is formed using multiple servo-controlled segments. The system uses **PCA9685 servo drivers** to efficiently control all motors and ensure smooth operation.

---

## 🚀 Features

- 🕒 Real-time clock display (HH:MM)
- 🔄 Smooth servo animations for digit transitions
- 📶 Wi-Fi enabled for Acurate time sync over NTP
- ⚡ Stable power management using SMPS
- 🧠 Efficient control using ESP32
- 🔧 Modular and scalable design

---

## 🧰 Hardware Requirements

| Component | Quantity |
|----------|--------|
| ESP32 Development Board | 1 |
| PCA9685 Servo Driver | 2 |
| SG90 / MG90 Servo Motors | 28 |
| 5V 20A (100W) SMPS Power Supply | 1 |
| Connecting Wires | As needed |
| Mounting Frame / Structure | 1 |

---

## 🔌 Circuit Connections

### ESP32 ↔ PCA9685 (I2C)
- SDA → GPIO 21  
- SCL → GPIO 22  

### PCA9685 Configuration
- First Driver Address: `0x40`
- Second Driver Address: `0x41` (via address pin)

### Power Supply
- Servos powered by **5V 20A SMPS**
- ESP32 powered via **USB or regulated 5V**
- **IMPORTANT:** Common ground between ESP32, PCA9685, and SMPS

---

## ⚙️ Software Requirements

- Arduino IDE
- ESP32 Board Package
- Required Libraries:
  - `Adafruit PWM Servo Driver`
  - `Wire.h`
  - `WiFi.h` (optional for NTP)
  - `NTPClient` (optional)

---

## 🧠 Working Principle

- Each digit (0–9) is composed of **7 segments**
- Each segment is controlled by a **servo motor**
- Servo rotates between:
  - **ON position → segment visible**
  - **OFF position → segment hidden**
- ESP32 calculates current time and updates servo positions accordingly

---

## 🔄 Servo Mapping

- Total Servos: **28**
- 4 Digits × 7 Segments = 28 Servos:
  - Digit Panel 1 → Servos 1–7
  - Digit Panel 2 → Servos 8–14
  - Digit Panel 3 → Servos 15–21
  - Digit Panel 4 → Servos 22–28

---

## ⚠️ Important Notes
- 🚫 Do NOT power servos from ESP32
- ⚡ Ensure SMPS can handle peak load (28 servos)
- 🔥 Use proper wiring to avoid voltage drops
- 🧯 Add capacitors if needed for stability
- 🔄 Calibrate each servo angle individually

---

## 🛠️ Future Improvements

- ⏳ Add seconds display
- 📱 Mobile app control
- 🔊 Sound feedback
- 🔋 Battery backup

---

## 📜 License

This project is licensed under the MIT License.

---
