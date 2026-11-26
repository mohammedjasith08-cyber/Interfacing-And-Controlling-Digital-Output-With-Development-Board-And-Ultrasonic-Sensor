# Interfacing Ultrasonic Sensor with Arduino UNO

## Aim

To interface an HC-SR04 ultrasonic sensor with an Arduino UNO development board and measure the distance of an object using ultrasonic waves.

## Components Required

1. Arduino UNO

2. HC-SR04 Ultrasonic Sensor

3. Breadboard

4. Jumper Wires

5. USB Cable

6. Computer with Arduino IDE

## Algorithm

1. Start the program.

2. Define the Trigger pin as pin 9 and Echo pin as pin 10.

3. Initialize the Trigger pin as OUTPUT and Echo pin as INPUT.

4. Initialize serial communication at 9600 baud rate.

5. Set the Trigger pin LOW for 2 microseconds.

6. Set the Trigger pin HIGH for 10 microseconds to transmit an ultrasonic pulse.

7. Set the Trigger pin LOW again.

8. Measure the time taken by the ultrasonic pulse to return using the Echo pin.

9. Calculate the distance using the measured duration.

10. Display the distance in centimeters through the Serial Monitor.

11. Wait for 500 milliseconds.

12. Repeat the process continuously.

## Procedure

1. Connect the VCC pin of the HC-SR04 ultrasonic sensor to the 5V pin of the Arduino UNO.

2. Connect the GND pin of the sensor to the GND pin of the Arduino.

3. Connect the TRIG pin of the sensor to digital pin 9 of the Arduino.

4. Connect the ECHO pin of the sensor to digital pin 10 of the Arduino.

5. Open Arduino IDE and write the program.

6. Select the Arduino UNO board and the appropriate COM port.

7. Upload the program to the Arduino UNO.

8. Open the Serial Monitor and set the baud rate to 9600.

9. Place an object in front of the ultrasonic sensor.

10. Observe the measured distance displayed in centimeters.

## Program

## Developed By : MOHAMMED JASITH J
## Register NUmber: 212225230180
```
const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.0343 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(500);
}
```

## Output

The distance of the object placed in front of the ultrasonic sensor is displayed in centimeters on the Serial Monitor.

<img width="424" height="534" alt="image" src="https://github.com/user-attachments/assets/b6aef7c1-4126-42b0-8d60-1f21026ff47b" />


<img width="430" height="533" alt="image" src="https://github.com/user-attachments/assets/ec3266a5-d3cf-4e89-8d87-d21dabfb5599" />


## Result

Thus, the HC-SR04 ultrasonic sensor was successfully interfaced with the Arduino UNO development board, and the distance of an object was measured and displayed in centimeters using ultrasonic waves.

