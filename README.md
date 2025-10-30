# 🌈 Arduino UNO PWM LED Fade

This project demonstrates how to control LED brightness using **PWM (Pulse Width Modulation)** on an **Arduino UNO**.  
The LED gradually **fades in and out**, showing smooth brightness transitions.

---

## 🧠 Overview

PWM allows us to simulate analog output using digital pins by varying the duty cycle of a square wave.  
In this project, the LED brightness increases from 0 to 255 and then decreases back to 0, creating a soft fade effect.

---

## ⚙️ Hardware Requirements

- Arduino UNO  
- USB Cable (Type-B)  
- LED  
- 220Ω resistor  
- Jumper wires  
- Breadboard  

---

## 🔌 Circuit Connection

| Component | Arduino Pin | Description |
|------------|-------------|-------------|
| LED (Anode +) | Pin 11 | PWM-capable pin |
| LED (Cathode -) | GND (via 220Ω resistor) | Current limiting |

⚠️ PWM pins on Arduino UNO are: **3, 5, 6, 9, 10, and 11**

---

## 🧾 Arduino Code

```cpp
const int pwmpin = 11; // PWM Pin (3, 5, 6, 9, 10, 11)
int i;

void setup() {
}

void loop() {
  for (i = 0; i < 255; i++) {
    analogWrite(pwmpin, i);
    delay(2);
  }
  delay(2000);
  for (i = 255; i > 0; i--) {
    analogWrite(pwmpin, i);
    delay(2);
  }
  delay(2000);
}
🚀 Upload Steps
Open Arduino IDE

Paste the above code

Select Board → Arduino UNO

Select the correct COM Port

Click Upload

The LED will fade in and out repeatedly every 2 seconds.

🧰 Tools Used
Arduino IDE (v2.0 or later)

GitHub Desktop (optional for version control)

🎨 Output Behavior
🔹 LED brightness increases gradually
🔹 LED brightness decreases smoothly
🔁 Continuous loop with a 2-second pause
