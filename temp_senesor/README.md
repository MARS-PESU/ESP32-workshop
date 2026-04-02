<img width="868" height="495" alt="image" src="https://github.com/user-attachments/assets/1a5fe553-91e8-49b4-abe3-0eb2260af85b" />

```cpp
#include <DHT.h>

#define DHTPIN 4       // GPIO where DATA is connected
#define DHTTYPE DHT11 // Sensor type

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(115200);
  dht.begin();
}

void loop() {
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature(); // Celsius

  // Check if reading failed
  if (isnan(humidity) || isnan(temperature)) {
    Serial.println("Failed to read from DHT11!");
    return;
  }

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");

  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.println(" %");

  delay(2000); // DHT11 needs slow sampling
}
```

<img width="881" height="743" alt="image" src="https://github.com/user-attachments/assets/91859704-6ac4-4400-b426-0ca4527db83f" />
