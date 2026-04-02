

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
