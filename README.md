# 02-Traffic-Light-System
An Arduino-based Traffic light system
Project 3: Traffic Light Controller

Description

This is my third Embedded Systems project in which I used an Arduino Uno to simulate a real traffic light system — the Red, Yellow, and Green LEDs turn ON/OFF in a fixed sequence, and at the end, the Green LED blinks 3 times (like a pedestrian warning signal).

Hardware Used

* Board: Arduino Uno
* Red LED
* Yellow LED
* Green LED
* Resistors: 220 ohm (for each LED)
* Breadboard
* Jumper wires


How It Works

All three LEDs are connected to separate digital pins — Red (Pin 8), Yellow (Pin 10), and Green (Pin 12). The code follows a sequence: first, the Red LED turns ON for 3 seconds, then the Yellow LED turns ON for 1 second (both LEDs are ON at the same time, just like in a real traffic light). Then, both LEDs turn OFF and the Green LED turns ON for 3 seconds. At the end, the Green LED blinks 3 times as a warning, and then the complete cycle repeats.

Code
cpp
// Traffic Light Controller for Arduino Uno
// Pins Setup:
// Red LED    -> Pin 8
// Yellow LED -> Pin 10
// Green LED  -> Pin 12
void setup() {
  pinMode(8, OUTPUT);  // Red LED
  pinMode(10, OUTPUT); // Yellow LED
  pinMode(12, OUTPUT); // Green LED
}
void loop() {
  // 1. Red Light Turn On
  digitalWrite(8, HIGH);
  delay(3000);
  // 2. Yellow Light Turn On
  digitalWrite(10, HIGH);
  delay(1000);
  // 3. Turn off Red and Yellow
  digitalWrite(8, LOW);
  digitalWrite(10, LOW);
  // 4. Green Light Turn On
  digitalWrite(12, HIGH);
  delay(3000);
  digitalWrite(12, LOW);
  delay(500);
  // 5. Green Light Blinking (Blink 3 times)
  digitalWrite(12, HIGH);
  delay(500);
  digitalWrite(12, LOW);
  delay(500);
  digitalWrite(12, HIGH);
  delay(500);
  digitalWrite(12, LOW);
  delay(500);
  digitalWrite(12, HIGH);
  delay(500);
  digitalWrite(12, LOW);
  delay(1000);
}

Demo Video

[Add the video link here]

What I Learned

* How to control multiple digital outputs at the same time
* How to convert a real-world system (traffic light) into code logic
* Sequential timing control using the delay() function
* How to create a repeated blinking pattern using loops
