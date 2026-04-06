# Ultrasonic Distance Sensor

This project uses an **ultrasonic sensor** to measure how far an object is from the sensor.

The sensor continuously checks the distance and displays the result on the screen in **centimeters (cm)**.

This is useful for creating **interactive objects and responsive spaces** that react based on how close a person or object is.

---

## What This Does

- Measures distance to nearby objects
- Displays the distance in centimeters
- Updates continuously in real time
- Useful for smart and interactive design prototypes

---

## Components Used

- ESP32 board
- Ultrasonic Sensor (HC-SR04)
- Jumper wires
- USB cable for power

---

## Working Idea

The ultrasonic sensor sends out a small sound wave that cannot be heard by humans.

It then waits for the sound to bounce back after hitting an object.

By calculating the return time, it estimates the distance.

- Object closer → smaller distance value
- Object farther → larger distance value

This creates a simple way to sense proximity and movement.

---

## Code

```cpp
#define TRIG_PIN 5
#define ECHO_PIN 18

long duration;
float distance;

void setup() {
  Serial.begin(115200);
  
  pinMode(TRIG_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
}

void loop() {
  // Clear trigger
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);

  // Send short pulse
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);

  // Read return signal
  duration = pulseIn(ECHO_PIN, HIGH);

  // Convert to distance
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(500);
}
```

---

## Output Preview

![Ultrasonic Sensor Output](https://github.com/user-attachments/assets/f28ab9ca-6c60-4bc6-b808-31200c614c7b)

The output screen continuously shows the measured distance in centimeters.

Example:

**Distance: 24.5 cm**

---

## Design Perspective

From a design perspective, this sensor can be used to create systems that respond to how close a user is.

Examples include:

- touchless interactive displays
- responsive lighting systems
- museum and exhibition installations
- smart furniture
- motion-reactive product design

This helps create more immersive and user-centered experiences.
