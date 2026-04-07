# Relay Switch Control

This project uses a **relay module** to switch an external device ON and OFF using the ESP32.

A relay works like an electronically controlled switch.  
It allows the ESP32 to control devices such as lights, fans, or other appliances.

In this experiment, the relay turns ON for **5 seconds** and OFF for **5 seconds**, repeating continuously.

---

## What This Does

- turns the relay ON
- waits for 5 seconds
- turns the relay OFF
- repeats continuously

This introduces the idea of **controlling external devices through digital signals**.

---

## Components Used

- ESP32 board
- relay module
- jumper wires
- USB cable for power

---

## Working Idea

The relay acts like a switch controlled by the ESP32.

- **HIGH** → relay turns ON
- **LOW** → relay turns OFF

When ON, the relay can complete the circuit for an external device.

When OFF, the connection is broken.

This allows digital systems to interact with physical products and environments.

---

## Code

```cpp
// relay.ino

const int relayPin = 2;

void setup() {
  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, LOW);
}

void loop() {
  digitalWrite(relayPin, HIGH);
  delay(5000);

  digitalWrite(relayPin, LOW);
  delay(5000);
}
```

---

## Output

The relay will switch:

- ON → 5 seconds
- OFF → 5 seconds
- repeats continuously

You may hear a **clicking sound** each time the relay switches.

This is normal and indicates the relay is working.

---

## Design Perspective

From a design perspective, this is useful for creating **smart control systems**.

Examples include:

- automatic lighting
- smart switches
- appliance control
- exhibition installations
- responsive room systems

This helps students understand how digital interfaces can control physical devices.

---

## Learning Outcome

This activity introduces:

**digital control → physical switching → real-world interaction**

which is essential in smart product and spatial design.

![WhatsApp Image 2026-04-07 at 2 36 25 PM](https://github.com/user-attachments/assets/cbb7fc28-158a-428c-8bf1-24c5b14a6b7c)

