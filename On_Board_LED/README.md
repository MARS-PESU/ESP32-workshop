# LED Blink (ESP32 Onboard LED)

This project uses the **built-in LED on the ESP32 board** to create a simple blinking light effect.

The LED turns **ON for 1 second** and **OFF for 1 second**, repeating continuously.

This is usually the **first experiment in any microcontroller workshop** because it helps students understand how the board sends output signals.

---

## What This Does

- Turns the onboard LED ON
- Waits for 1 second
- Turns the LED OFF
- Repeats continuously

This is the most basic way to test whether the board is working correctly.

---

## Components Used

- ESP32 board
- USB cable for power and programming

> No external components are required because the LED is already built into the board.

---

## Working Idea

The ESP32 sends a signal to its onboard LED pin.

- **HIGH** → LED turns ON
- **LOW** → LED turns OFF

The delay creates a pause so the blinking is clearly visible.

This introduces the idea of **digital output and timing**.

---

## Code

```cpp
// ESP32 onboard LED blink code

const int ledPin = 2;   // Most ESP32 boards use GPIO 2 for onboard LED

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);  // LED ON
  delay(1000);                 // Wait 1 second

  digitalWrite(ledPin, LOW);   // LED OFF
  delay(1000);                 // Wait 1 second
}
```

---

## Output

The onboard LED will blink like this:

- ON → 1 second
- OFF → 1 second
- repeats continuously

This creates a simple flashing light pattern.

---

## Design Perspective

From a design perspective, this introduces the idea of **visual feedback**.

Examples include:

- notification lights
- status indicators
- interactive light signals
- prototype feedback systems
- responsive lighting elements

This is often the first step before moving to more complex interactive systems.
