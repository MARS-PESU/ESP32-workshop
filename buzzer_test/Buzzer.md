
``` cpp
#define BUZZER_PIN 25

void setup() {
  pinMode(BUZZER_PIN, OUTPUT);
}

void loop() {
  digitalWrite(BUZZER_PIN, HIGH); // ON
  delay(200);                     // short beep

  digitalWrite(BUZZER_PIN, LOW);  // OFF
  delay(800);                     // pause
}
```
