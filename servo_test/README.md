# Servo Motor Movement Control

This project uses a **servo motor** to create controlled rotational movement.

The motor automatically moves between **0°, 90°, and 180°**, pausing briefly at each position.

This helps in understanding how movement and motion can be integrated into interactive product and spatial design.

---

## What This Does

- Rotates the servo motor to different angles
- Moves in fixed steps: 0°, 90°, and 180°
- Repeats the motion continuously
- Useful for kinetic and responsive design prototypes

---

## Circuit

<img width="951" height="618" alt="image" src="https://github.com/user-attachments/assets/5f9faf00-7eeb-4226-8707-7f4e6001544b" />



## Components Used

- ESP32 board
- Servo motor
- Jumper wires
- USB cable for power
- ESP32Servo library

---

## Library Setup Steps

Before uploading the code, install the **ESP32Servo** library.

### Step 1: Open Library Manager
In Arduino IDE, go to:

**Sketch → Include Library → Manage Libraries**

---

### Step 2: Search the Library
In the search box, type:

`esp32servo`

---

### Step 3: Install
Select **ESP32Servo** and click **Install**

---

### Step 4: Add to Code
At the top of your code, include:

```cpp
#include <ESP32Servo.h>
```

---

## Library Installation Preview

![Library Installation](https://github.com/user-attachments/assets/be1695ba-e759-4c63-bf86-75626dfd9348)

This library helps control smooth motor rotation using the ESP32 board.

---

## Working Idea

A servo motor moves to specific angles rather than spinning continuously.

In this project, it moves between:

- **0°** → starting position
- **90°** → halfway rotation
- **180°** → full rotation

After reaching each angle, it pauses for 2 seconds.

This creates controlled mechanical motion that can be used in interactive design systems.

---

## Code

```cpp
#include <ESP32Servo.h>

#define SERVO_PIN 13

Servo myServo;

void setup() {
  Serial.begin(115200);

  myServo.attach(SERVO_PIN);
}

void loop() {
  Serial.println("0 degrees");
  myServo.write(0);
  delay(2000);

  Serial.println("90 degrees");
  myServo.write(90);
  delay(2000);

  Serial.println("180 degrees");
  myServo.write(180);
  delay(2000);
}
```

---

## Output Preview

![Servo Output](https://github.com/user-attachments/assets/4dd8ea2c-24d0-4586-b369-db0f04e09b13)

The serial monitor displays the current angle while the servo moves physically to that position.

Example:

- 0 degrees
- 90 degrees
- 180 degrees

---

## Design Perspective

From a design perspective, this can be used to create **moving and responsive physical elements**.

Examples include:

- automated product parts
- movable panels
- interactive exhibition elements
- smart furniture components
- kinetic art installations

This helps introduce motion and physical interaction into design prototypes.
