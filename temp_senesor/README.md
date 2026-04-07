# Temperature and Humidity Sensor (DHT11)

This project uses a **DHT11 sensor** to measure the surrounding **temperature** and **humidity**.

The sensor continuously reads the environment and displays the values on the screen every few seconds.

This is useful for creating **smart environments, responsive installations, and environmental monitoring designs**.

---

## What This Does

- Measures room temperature
- Measures humidity level in the air
- Displays live readings
- Updates every 2 seconds
- Useful for interactive and smart design prototypes

---

## Circuit

<img width="506" height="348" alt="image" src="https://github.com/user-attachments/assets/69c4247f-d8af-4336-8e0b-ff5995cc2c27" />


## Components Used

- ESP32 board
- DHT11 sensor
- Jumper wires
- USB cable for power
- DHT sensor library

---

## Library Setup Steps

Before uploading the code, install the **DHT sensor library**.

### Step 1: Open Library Manager
In Arduino IDE, go to:

**Sketch → Include Library → Manage Libraries**

---

### Step 2: Search the Library
In the search box, type:

`DHT sensor library`

---

### Step 3: Install
Select **DHT sensor library by Adafruit** and click **Install**

---

### Step 4: Add to Code
At the top of your code, include:

```cpp
#include <DHT.h>
```

---

## Library Installation Preview

![Library Installation](https://github.com/user-attachments/assets/1a5fe553-91e8-49b4-abe3-0eb2260af85b)

This library allows the ESP32 to read temperature and humidity data from the DHT11 sensor.

---

## Working Idea

The DHT11 sensor reads the surrounding air conditions.

It provides two values:

- **Temperature** → measured in °C
- **Humidity** → measured in %

The system checks these values every 2 seconds and prints them on the serial monitor.

Example:

- Temperature: 29 °C
- Humidity: 62 %

This helps in understanding environmental sensing in design applications.

---

## Code

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

---

## Output Preview

![Sensor Output](https://github.com/user-attachments/assets/91859704-6ac4-4400-b426-0ca4527db83f)

The serial monitor continuously displays temperature and humidity readings.

Example:

- Temperature: 28 °C
- Humidity: 65 %

---

## Design Perspective

From a design perspective, this sensor can be used to create **environment-aware systems**.

Examples include:

- climate-responsive interiors
- smart room installations
- museum environment monitoring
- interactive displays reacting to room conditions
- product prototypes that respond to heat or moisture

This helps create spaces and products that respond to the surrounding environment.
