// ESP32 PWM Buzzer Example
// Connect buzzer + to GPIO 18
// Connect buzzer - to GND

const int buzzerPin = 18;

// Frequencies for different tunes
int tunes[] = {
  262, // C4
  294, // D4
  330, // E4
  349, // F4
  392, // G4
  440, // A4
  494, // B4
  523  // C5
};

int currentTune = 0;
const int totalTunes = sizeof(tunes) / sizeof(tunes[0]);

void setup() {
  // Attach PWM to buzzer pin
  // ledcAttach(pin, frequency, resolution)
  ledcAttach(buzzerPin, tunes[currentTune], 8);
}

void loop() {
  // Play current tune
  ledcWriteTone(buzzerPin, tunes[currentTune]);

  delay(1000);

  // Stop buzzer
  ledcWriteTone(buzzerPin, 0);

  delay(300);

  // Move to next tune
  currentTune++;

  // Restart from beginning after last tune
  if (currentTune >= totalTunes) {
    currentTune = 0;
  }
}
