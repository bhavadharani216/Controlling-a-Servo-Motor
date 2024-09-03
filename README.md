# Controlling-a-Servo-Motor
task 1 code:



#include <Servo.h>  // Include the Servo library

// Create a Servo object
Servo myServo;

// Define LED pin
const int ledPin = 13;

void setup() {
  myServo.attach(9);    // Attach the servo to pin 9
  pinMode(ledPin, OUTPUT);  // Set LED pin as an output
}

void loop() {
  // Sweep from 0 to 180 degrees
  for (int angle = 0; angle <= 180; angle++) {
    myServo.write(angle);  // Set the servo to the current angle
    digitalWrite(ledPin, HIGH); // Turn LED on
    delay(15);             // Wait for the servo to reach the position
    digitalWrite(ledPin, LOW);  // Turn LED off
    delay(15);             // Brief delay before the next position
  }

  // Sweep from 180 to 0 degrees
  for (int angle = 180; angle >= 0; angle--) {
    myServo.write(angle);  // Set the servo to the current angle
    digitalWrite(ledPin, HIGH); // Turn LED on
    delay(15);             // Wait for the servo to reach the position
    digitalWrite(ledPin, LOW);  // Turn LED off
    delay(15);             // Brief delay before the next position
  }
}
