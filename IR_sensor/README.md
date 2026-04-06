# IR Obstacle Detection Sensor

This project uses an **IR (Infrared) sensor** to check whether an object is present in front of it.

The sensor continuously looks for obstacles.  
When something comes close, it shows the message:

**Obstacle Detected!**

If nothing is in front of the sensor, it shows:

**No Obstacle**

This helps in understanding how sensors can be used in interactive products, installations, and smart design systems.

---

## What This Does

- Detects nearby objects
- Sends a simple message to the screen
- Updates every few milliseconds
- Useful for interactive design prototypes

---

## Components Used

- ESP32 board
- IR Sensor
- Jumper wires
- USB cable for power

---

## Working Idea

The IR sensor emits infrared light and checks whether it reflects back.

- If reflection is detected → **Obstacle Detected**
- If no reflection → **No Obstacle**

This is commonly used in:

- automatic doors
- touchless displays
- smart bins
- motion-based installations
- interactive exhibition designs

---

## Code

```cpp
#define IR_PIN 15

void setup() {
  Serial.begin(115200);
  pinMode(IR_PIN, INPUT);
}

void loop() {
  int sensorValue = digitalRead(IR_PIN);

  if (sensorValue == LOW) {
    Serial.println("Obstacle Detected!");
  } else {
    Serial.println("No Obstacle");
  }

  delay(200);
}
```

## Circuit

<img width="604" height="584" alt="image" src="https://github.com/user-attachments/assets/dfaf2265-0c04-4fa8-9c61-df1529f0a230" />


---

## Output Preview

![IR Sensor Output](https://github.com/user-attachments/assets/ef0f47e5-cf8d-4381-81a4-089cc513a91e)

The screen keeps updating with live messages depending on whether an object is near the sensor.

---

## Design Perspective

From a design point of view, this can be used to create **responsive environments** where the space reacts to people’s movement.

Examples include:

- lights turning on when someone approaches
- digital screens reacting to hand gestures
- exhibition objects triggering sound or visuals
- smart furniture interaction

This makes physical spaces feel more interactive and user-friendly.
