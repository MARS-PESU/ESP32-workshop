# LED Brightness Control (PWM Fade)

This project uses the **ESP32 onboard LED** to create a smooth **fade in and fade out light effect**.

Instead of simply turning the LED ON and OFF, the brightness changes gradually, creating a soft transition.

This helps students explore how light intensity can be controlled for interactive design applications.

---

## What This Does

- gradually increases LED brightness
- gradually decreases LED brightness
- creates a smooth fading light effect
- repeats continuously

This introduces the concept of **controlled visual output**.

---

## Components Used

- ESP32 board
- USB cable for power

> No external LED is required if your ESP32 board has an onboard LED.

---

## Working Idea

The ESP32 uses **PWM (Pulse Width Modulation)** to control brightness.

Instead of only ON or OFF, the LED can glow at different intensity levels.

Brightness values range from:

- **0** → completely OFF
- **255** → maximum brightness

The code slowly moves through these values to create a smooth light transition.

---

## Code

```cpp
// ESP32 PWM LED brightness control

const int ledPin = 2;        // LED connected to GPIO 2
const int pwmChannel = 0;    
const int freq = 5000;       
const int resolution = 8;    // 8-bit resolution (0 to 255)

void setup() {
  // Configure PWM
  ledcSetup(pwmChannel, freq, resolution);
  
  // Attach the LED pin to the PWM channel
  ledcAttachPin(ledPin, pwmChannel);
}

void loop() {
  // Increase brightness
  for (int dutyCycle = 0; dutyCycle <= 255; dutyCycle++) {
    ledcWrite(pwmChannel, dutyCycle);
    delay(10);
  }

  // Decrease brightness
  for (int dutyCycle = 255; dutyCycle >= 0; dutyCycle--) {
    ledcWrite(pwmChannel, dutyCycle);
    delay(10);
  }
}
```

---

## Output

The LED will:

- slowly brighten
- reach full intensity
- slowly dim
- repeat continuously

This creates a breathing or fading light effect.

---

## Design Perspective

From a design perspective, this is useful for **ambient and responsive lighting systems**.

Examples include:

- mood lighting
- notification glow effects
- exhibition light transitions
- product status indicators
- interactive installations

This helps students explore how subtle visual feedback can improve user experience.

---

## Learning Outcome

This activity introduces:

**intensity control + smooth transitions + visual feedback**

which are important in lighting and interaction design.
