```cpp
#include <WiFi.h>

// Replace with your credentials
const char* ssid = "YOUR_SSID";
const char* password = "YOUR_PASSWORD";

// Web server on port 80
WiFiServer server(80);

// LED pin
const int ledPin = 2;
String ledState = "OFF";

void setup() {
  Serial.begin(115200);
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);

  // Connect to WiFi
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, password);

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println("\nWiFi connected!");
  Serial.println("IP Address: ");
  Serial.println(WiFi.localIP());

  server.begin();
}

void loop() {
  WiFiClient client = server.available();

  if (client) {
    Serial.println("New Client Connected");
    String currentLine = "";

    while (client.connected()) {
      if (client.available()) {
        char c = client.read();
        Serial.write(c);

        // Detect request
        if (c == '\n') {
          if (currentLine.length() == 0) {

            // HTTP response
            client.println("HTTP/1.1 200 OK");
            client.println("Content-type:text/html");
            client.println("Connection: close");
            client.println();

            // Webpage
            client.println("<!DOCTYPE html><html>");
            client.println("<head><meta name='viewport' content='width=device-width, initial-scale=1'>");
            client.println("<style>button{padding:15px;font-size:20px;margin:5px;}</style></head>");
            client.println("<body><h1>ESP32 LED Control</h1>");

            client.println("<p>LED State: " + ledState + "</p>");

            client.println("<a href=\"/ON\"><button>ON</button></a>");
            client.println("<a href=\"/OFF\"><button>OFF</button></a>");

            client.println("</body></html>");
            client.println();
            break;
          } else {
            currentLine = "";
          }
        } 
        else if (c != '\r') {
          currentLine += c;
        }

        // Handle requests
        if (currentLine.endsWith("GET /ON")) {
          digitalWrite(ledPin, HIGH);
          ledState = "ON";
        }
        if (currentLine.endsWith("GET /OFF")) {
          digitalWrite(ledPin, LOW);
          ledState = "OFF";
        }
      }
    }

    client.stop();
    Serial.println("Client Disconnected");
  }
}
```
