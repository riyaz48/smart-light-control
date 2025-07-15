# smart-light-control
char command;

void setup() {
  pinMode(13, OUTPUT);  // LED pin
  Serial.begin(9600);   // Bluetooth baud rate
}

void loop() {
  if (Serial.available()) {
    command = Serial.read();

    if (command == '1') {
      digitalWrite(13, HIGH); // Turn ON LED
    } else if (command == '0') {
      digitalWrite(13, LOW);  // Turn OFF LED
    }
  }
}
