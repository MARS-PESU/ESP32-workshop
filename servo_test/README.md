<img width="888" height="508" alt="image" src="https://github.com/user-attachments/assets/be1695ba-e759-4c63-bf86-75626dfd9348" />


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

<img width="564" height="569" alt="image" src="https://github.com/user-attachments/assets/4dd8ea2c-24d0-4586-b369-db0f04e09b13" />
