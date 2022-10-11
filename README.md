# First-Arduino-Set-Up
Meant to test Arduino code from Arduino Editor
[Start code]

 include <Servo.h>
  Servo servo;
  const int servo_pin = 9;
  const int SW_pin = 2;
  const int X_pin = 0;
  const int Y_pin = 1;

void setup() {
    servo.attach(servo_pin);
    pinMode(SW_pin, INPUT);
    digitalWrite(SW_pin, HIGH);
    Serial.begin(9600);
}

	void loop() {
    /*servo.write(90);
    delay(1000);
    servo.write(180);
    delay(2000);
    servo.write(0);
    delay(2000);
    
     for(int pos = 0; pos < 180; pos += 5){
      servo.write(pos);
      delay(1000);
    }
    */
    /*
    Serial.print("Switch: ");
    Serial.print(digitalRead(SW_pin));
    
    Serial.print("\n");
    Serial.print("X-axis: ");
    Serial.print(analogRead(X_pin));
    
    Serial.print("\n");
    Serial.print("Y-axis: ");
    Serial.print(analogRead(Y_pin));
    Serial.print("\n\n");
    delay(500);
    */
    
    int xVal  = analogRead(X_pin);
    xVal = map(xVal, 0, 1023, 0, 180);
    servo.write(xVal);
    delay(250);
    
    
    int yVal = analogRead(Y_pin);
    yVal = map(yVal, 0, 1023, 0, 180);
    servo.write(yVal);
    delay(250);
}


[End Code]
