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

<img width="850" height="626" alt="image" src="https://github.com/user-attachments/assets/ef0f47e5-cf8d-4381-81a4-089cc513a91e" />

