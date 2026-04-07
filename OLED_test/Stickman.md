``` cpp
//STICKMAN
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET -1

Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

int frame = 0;

void drawStickman(int x, int y, int pose, bool facingRight)
{
  int dir = facingRight ? 1 : -1;

  switch (pose)
  {
    case 0: // Standing
      display.drawCircle(x, y - 12, 4, WHITE);
      display.drawLine(x, y - 8, x, y + 8, WHITE);
      display.drawLine(x, y - 4, x - 6 * dir, y + 2, WHITE);
      display.drawLine(x, y - 4, x + 6 * dir, y + 2, WHITE);
      display.drawLine(x, y + 8, x - 5, y + 15, WHITE);
      display.drawLine(x, y + 8, x + 5, y + 15, WHITE);
      break;

    case 1: // Punch
      display.drawCircle(x, y - 12, 4, WHITE);
      display.drawLine(x, y - 8, x, y + 8, WHITE);
      display.drawLine(x, y - 4, x + 12 * dir, y - 2, WHITE);
      display.drawLine(x, y - 4, x - 6 * dir, y + 2, WHITE);
      display.drawLine(x, y + 8, x - 5, y + 15, WHITE);
      display.drawLine(x, y + 8, x + 5, y + 15, WHITE);
      break;

    case 2: // Kick
      display.drawCircle(x, y - 12, 4, WHITE);
      display.drawLine(x, y - 8, x, y + 8, WHITE);
      display.drawLine(x, y - 4, x - 6 * dir, y + 2, WHITE);
      display.drawLine(x, y - 4, x + 6 * dir, y + 2, WHITE);
      display.drawLine(x, y + 8, x - 5, y + 15, WHITE);
      display.drawLine(x, y + 8, x + 12 * dir, y + 4, WHITE);
      break;

    case 3: // Jump Kick
      display.drawCircle(x, y - 20, 4, WHITE);
      display.drawLine(x, y - 16, x, y, WHITE);
      display.drawLine(x, y - 12, x - 6 * dir, y - 6, WHITE);
      display.drawLine(x, y - 12, x + 6 * dir, y - 6, WHITE);
      display.drawLine(x, y, x - 5, y + 8, WHITE);
      display.drawLine(x, y, x + 14 * dir, y - 2, WHITE);
      break;

    case 4: // Duck
      display.drawCircle(x, y - 6, 4, WHITE);
      display.drawLine(x, y - 2, x, y + 8, WHITE);
      display.drawLine(x, y + 1, x - 6 * dir, y + 5, WHITE);
      display.drawLine(x, y + 1, x + 6 * dir, y + 5, WHITE);
      display.drawLine(x, y + 8, x - 4, y + 12, WHITE);
      display.drawLine(x, y + 8, x + 4, y + 12, WHITE);
      break;

    case 5: // Fallen Back
      display.drawCircle(x - 8 * dir, y + 10, 4, WHITE);
      display.drawLine(x - 4 * dir, y + 10, x + 10 * dir, y + 10, WHITE);
      display.drawLine(x + 2 * dir, y + 10, x + 8 * dir, y + 4, WHITE);
      display.drawLine(x + 2 * dir, y + 10, x + 8 * dir, y + 16, WHITE);
      display.drawLine(x + 10 * dir, y + 10, x + 16 * dir, y + 4, WHITE);
      display.drawLine(x + 10 * dir, y + 10, x + 16 * dir, y + 16, WHITE);
      break;
  }
}

void setup()
{
  if (!display.begin(SSD1306_SWITCHCAPVCC, 0x3C))
  {
    while (true);
  }
}

void loop()
{
  display.clearDisplay();
  display.drawLine(0, 55, 127, 55, WHITE);

  switch (frame)
  {
    case 0:
      drawStickman(30, 40, 0, true);
      drawStickman(95, 40, 0, false);
      break;

    case 1:
      drawStickman(35, 40, 1, true);
      drawStickman(90, 40, 4, false);
      display.drawCircle(65, 28, 2, WHITE);
      break;

    case 2:
      drawStickman(40, 40, 2, true);
      drawStickman(88, 40, 5, false);
      display.drawLine(68, 24, 72, 30, WHITE);
      display.drawLine(72, 24, 68, 30, WHITE);
      break;

    case 3:
      drawStickman(45, 40, 3, true);
      drawStickman(85, 40, 5, false);
      display.drawCircle(72, 20, 3, WHITE);
      break;

    case 4:
      drawStickman(40, 40, 4, true);
      drawStickman(80, 40, 1, false);
      display.drawCircle(60, 32, 2, WHITE);
      break;

    case 5:
      drawStickman(35, 40, 5, true);
      drawStickman(75, 40, 2, false);
      display.drawLine(55, 35, 62, 28, WHITE);
      break;

    case 6:
      drawStickman(30, 40, 5, true);
      drawStickman(70, 40, 0, false);
      break;

    case 7:
      drawStickman(40, 40, 0, true);
      drawStickman(80, 40, 0, false);
      break;
  }

  frame++;
  if (frame > 7)
    frame = 0;

  display.display();
  delay(250);
}
```
