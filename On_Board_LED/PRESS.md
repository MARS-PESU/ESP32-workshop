# Button Press Detection

This project uses a **push button** as an input device to control the **ESP32 onboard LED**.

When the button is pressed, the LED turns ON and a message is shown on the screen.

When the button is not pressed, the LED remains OFF.

This helps students understand how physical interaction can be used to trigger digital responses.

---

## What This Does

- detects button press
- turns LED ON when pressed
- turns LED OFF when released
- displays button status on screen

This is one of the simplest examples of **human interaction with hardware**.

---

## Components Used

- ESP32 board
- push button
- jumper wires
- USB cable for power

---

## Working Idea

The button acts as an **input control**.

When the button is pressed:

- LED turns ON
- serial monitor shows **Button Pressed**

When the button is released:

- LED turns OFF
- serial monitor shows **Button Not Pressed**

This introduces the idea of **input and response systems**.

---

## Code

```cpp
// ESP32 button press detection code

const int buttonPin = 4;   // Connect button to GPIO 4
const int ledPin = 2;      // Onboard LED pin

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Use internal pull-up resistor
  pinMode(ledPin, OUTPUT);

  Serial.begin(115200);
}

void loop() {
  int buttonState = digitalRead(buttonPin);

  // Button pressed
  if (buttonState == LOW) {
    digitalWrite(ledPin, HIGH);
    Serial.println("Button Pressed");
  } else {
    digitalWrite(ledPin, LOW);
    Serial.println("Button Not Pressed");
  }

  delay(100);
}
```

---

## Circuit

<img width="536" height="336" alt="image" src="https://github.com/user-attachments/assets/c34e03c9-e979-4dad-9b68-7f3b6a09dec9" />


## Output

When the button is pressed:

- LED turns ON
- message: **Button Pressed**

When released:

- LED turns OFF
- message: **Button Not Pressed**

The system checks the button continuously.

---

## Design Perspective

From a design perspective, this is the foundation of **interactive products and responsive interfaces**.

Examples include:

- smart switches
- touch-based installations
- interactive kiosks
- exhibition triggers
- product control buttons

This helps students understand how users physically interact with designed systems.

---

## Learning Outcome

This activity introduces the concept of:

**user input → system response**

which is central to interaction and product design.
