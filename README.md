# ESP32 - 7-Segment Display & Potentiometer with ADC

This project demonstrates how to use a **4-digit 7-segment display** combined with a **potentiometer** and a **push button**, all controlled by an **ESP32** using **FreeRTOS**.

## 🧠 Educational Purpose

- Dynamically display a value on a 7-segment display.
- Read an analog value using the **ADC** (Analog-to-Digital Converter).
- Handle a **push button with debouncing** to increment a counter.
- Use **FreeRTOS tasks** to manage these functions in parallel.

---

## 🔧 Required Hardware

- ESP32 DevKit
- 4-digit 7-segment display 3461BS-1 (manually wired)
- B10K Potentiometer
- Push button
- LED (integrated)
- Jumper wires, breadboard

---

## ⚙️ How It Works

- When the **push button** is pressed, a counter is incremented.
- This counter is displayed on the **4-digit display**.
- The **potentiometer** controls the **brightness of the display** (or another variable via the ADC).
- An **LED** reflects the button state (on = not pressed, off = pressed).

---

## 🗂️ Code Structure

| File          | Role |
|---------------|------|
| `main.c`      | Contains the main application logic |
| `display.h` / `display.c` | Handles the 7-segment display |

---

## 📷 Aperçu

<img src="https://github.com/user-attachments/assets/34c6a88e-ba9f-4614-91bb-4f9c0918be46" alt="1000021258" width="500"/>

---
## 🚀 Quick Start

1. Clone this repository
2. Flash the program:
   ```bash
   platformio run
