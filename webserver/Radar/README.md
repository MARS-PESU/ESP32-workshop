# Radar esp32 pbased
first 

``` cpp
#include <WiFi.h>
#include <WebServer.h>
#include <ESP32Servo.h>

const char* ssid = "herman";
const char* password = "12345678";

WebServer server(80);
Servo radarServo;

const int trigPin = 5;
const int echoPin = 18;
const int servoPin = 13;

int angle = 0;
int direction = 1;

long getDistance() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH, 30000);
  long distance = duration * 0.034 / 2;

  if (distance == 0 || distance > 200) {
    distance = 200;
  }

  return distance;
}

void handleData() {
  long distance = getDistance();

  String json = "{";
  json += "\"angle\":" + String(angle) + ",";
  json += "\"distance\":" + String(distance);
  json += "}";

  server.send(200, "application/json", json);
}

void setup() {
  Serial.begin(115200);

  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  radarServo.attach(servoPin);

  WiFi.begin(ssid, password);

  Serial.print("Connecting to WiFi");

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println();
  Serial.println("Connected to WiFi");
  Serial.print("ESP32 IP Address: ");
  Serial.println(WiFi.localIP());

  server.on("/data", handleData);

  server.begin();
}

void loop() {
  server.handleClient();

  radarServo.write(angle);

  angle += direction;

  if (angle >= 180) {
    direction = -1;
  }

  if (angle <= 0) {
    direction = 1;
  }

  delay(30);
}

// ESP32.ino
```
