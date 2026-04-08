# Radar ESP32 powered

## Circuit 

<img width="1125" height="771" alt="image" src="https://github.com/user-attachments/assets/a09f4a9c-67a0-472d-a454-812d81e26553" />

## Code 

```cpp
#include <WiFi.h>
#include <WebServer.h>
#include <ESP32Servo.h>

// ================= WIFI =================
const char* ssid = "YOUR_SSID";
const char* password = "YOUR_PSWD";

// ================= PINS =================
#define LED 2
#define TrigPin 5
#define EchoPin 18
#define SoundSpeed 0.034

WebServer server(80);
Servo servo;

// ================= GLOBALS =================
float distance = 0;
unsigned long previousMillis = 0;
unsigned long currentMillis;
int period = 80;
int servoAngle = 90;
bool servoDirection = true;

// ================= WEB =================
void handleRoot() {
  server.send(200, "text/plain", "ESP32 Radar API Running");
}

// 🔥 FIXED: CORS ENABLED
void handleDistance() {
  String data = "[\"" + String(distance) + "\",\"" + String(servoAngle) + "\"]";

  server.sendHeader("Access-Control-Allow-Origin", "*");
  server.sendHeader("Access-Control-Allow-Methods", "GET");
  server.sendHeader("Access-Control-Allow-Headers", "*");

  server.send(200, "application/json", data);
}

// ================= SENSOR =================
void readDistance() {
  digitalWrite(TrigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(TrigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(TrigPin, LOW);

  long duration = pulseIn(EchoPin, HIGH, 30000); // timeout

  if (duration == 0) return;

  distance = duration * SoundSpeed / 2;
}

// ================= SERVO =================
void updateServo() {
  currentMillis = millis();

  if (servoAngle >= 165) servoDirection = false;
  if (servoAngle <= 15)  servoDirection = true;

  if (currentMillis - previousMillis >= period) {

    servoAngle += (servoDirection ? 1 : -1);
    servo.write(servoAngle);

    readDistance();

    Serial.print("Distance: ");
    Serial.print(distance);
    Serial.print(" cm | Angle: ");
    Serial.println(servoAngle);

    previousMillis = currentMillis;
  }
}

// ================= SETUP =================
void setup() {
  Serial.begin(115200);

  pinMode(TrigPin, OUTPUT);
  pinMode(EchoPin, INPUT);
  pinMode(LED, OUTPUT);

  servo.attach(13);
  servo.write(servoAngle);

  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);

  while (WiFi.status() != WL_CONNECTED) {
    digitalWrite(LED, !digitalRead(LED));
    delay(300);
    Serial.print(".");
  }

  digitalWrite(LED, HIGH);

  Serial.println("\nConnected!");
  Serial.print("ESP32 IP Address: ");
  Serial.println(WiFi.localIP());

  // Routes
  server.on("/", handleRoot);
  server.on("/readDistance", handleDistance);

  server.begin();
  Serial.println("HTTP server started");
}

// ================= LOOP =================
void loop() {
  server.handleClient();
  updateServo();
}
```
