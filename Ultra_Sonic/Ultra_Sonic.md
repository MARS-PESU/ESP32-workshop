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

const int trigPin = 5;
const int echoPin = 18;

//define sound speed in cm/uS
#define SOUND_SPEED 0.034
#define CM_TO_INCH 0.393701

long duration;
float distanceCm;
float distanceInch;

void setup() {
  Serial.begin(115200); // Starts the serial communication
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input
}

void loop() {
  // Clears the trigPin
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  // Sets the trigPin on HIGH state for 10 micro seconds
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  // Reads the echoPin, returns the sound wave travel time in microseconds
  duration = pulseIn(echoPin, HIGH);
  
  // Calculate the distance
  distanceCm = duration * SOUND_SPEED/2;
  
  // Convert to inches
  distanceInch = distanceCm * CM_TO_INCH;
  
  // Prints the distance in the Serial Monitor
  Serial.print("Distance (cm): ");
  Serial.println(distanceCm);
  Serial.print("Distance (inch): ");
  Serial.println(distanceInch);
  
  delay(1000);
}
```

## Circuit

<img width="846" height="688" alt="image" src="https://github.com/user-attachments/assets/6402acc5-1dc3-4969-8884-a860c4dbe5b9" />


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
