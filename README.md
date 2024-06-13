# IoT Workshop-2024
## ETCE LAB


[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Welcoming
Welcome to the Internet of Things (IoT) Workshop!
# Introduction
Throughout this workshop,we’ll embark on a journey through the fundamentals of IoT, starting with an overview of what IoT is and how it’s being use in
different industries especially in mining.
# what you will learn

- Experience with popular microcontrollers such as the Arduino Nano 33 and Arduino Uno
- Being able to work with various sensors
- Foundational coding skills, including essential functions and techniques,necessary for IoT projects.


## Attention
Please remember this for all experiments.
- Treat the equipment very gently.
- Look at the diagram first to see how the wires and sensors connect to the Arduino.
- Always ask questions.
- We will begin coding after double-checking that the wires and sensors are correctly connected to the Arduino.
- Try to learn the codes and keep questioning the tutor.
- When you completely understand the codes, start typing them in the Arduino-related software.
- Look optimistically. If you did not have any errors.
- Then connect the Arduino hardware to the computer with the related cable.
- Finally, you upload the codes to Arduino.

*Thank you very much**
## let's start :) 
## 1-Detecting fire
we will learn how to detect fire using a flame sensor.
# Components and supplies:
- Flame Sensor (model with an analog out) -> These types of sensors are used for short range fire detection(up to about
3 feet)
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/128.jpg)


- Male to female jumper wires
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/129.jpg)


- An arduino, any flavor
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/333.jpeg)
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/125.jpg)


- Lighter or another flame source for testing
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/126.jpg)
NOTE : If you are using arduino nano 33, then you need to use " BreadBoard"also.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/127.jpg)


Important pins in EVERY arduino
- VCC --> positive voltage input: 5v for analog and 3.3v for digital
- A0 --> analog output
- D0 --> digital output
- GND --> ground

Wiring to an arduino:
To wire the flame sensor to the arduino simply connect the following as shown:
- flame sensor -> arduino
- VCC -> 5v
- GND -> GND
- A0 -> Analog in 0 
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/134.jpg)


```python
// lowest and highest sensor readings :
const int sensorMin = 0;
// sensor minimum
const int sensorMax = 1024; // sensor maximum
void ---- () {
// initialize serial communication @ 9600 baud :
Serial . begin (9600);
}
void ---- () {
// read the sensor on analog A0 :
int sensorReading = analogRead ( A0 );
// map the sensor range ( four options ):
// ex : ’ long int map ( long int , long int ,
// long int , long int , long int ) ’
int range = map ( sensorReading , sensorMin , sensorMax ,0 ,3);
// range value :
switch ( range ) {
case 0:
// A fire closer than 1.5 feet away .
Serial . println ( " ** Close Fire ** " );
break ;
case 1:
// A fire between 1 -3 feet away .
---------------( " ** Distant Fire ** " );
break ;
case 2:
// No fire detected .
---------------( " No Fire " );
break ;
}
delay (1); // delay between reads
}
```
## 2- Smoke Detector
we will learn how to create a smoke detector using gas sensor.
# Components and supplies:
- Resistor 220 ohm
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/131.jpg)


- Gas sensor 
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/132.jpg)


- An arduino, any flavor
- Buzzer
A buzzer is an electronic device that emits sound when it is powered bya 5-volt electrical current. These buzzers are commonly used in alarms, timers, confirmation of user input.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/123.jpg)

- Breadborad
- Jumper wires
# Wiring to an Arduino:
To wire the smoke sensor to the Arduino simply connect the following as
shown:
Gas Detection sensor connection :
- vcc -> 5v 
- GND -> GND
- A0 -> A0 
Buzzer connection :
- long pin of buzzer -> D8
- short pin of buzzer -> GND
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/121.jpg)

```python
const int gasSensorPin = --- ; 
const int buzzerPin = 8; 
const int gasThreshold = 300;   
void setup() {
  Serial.begin(9600);
  pinMode(gasSensorPin, ---);
  pinMode(buzzerPin, ---);
  Serial.println("Gas sensor and buzzer test initialized.");
}
void loop() {
  int sensorValue = analogRead(gasSensorPin);
  Serial.print("Gas Sensor Value: ");
  Serial.println(sensorValue);
  if (sensorValue > gasThreshold) {
    digitalWrite(buzzerPin, ---); 
  } else {
    digitalWrite(buzzerPin, ---); 
  }
  delay(1000);
}

```
## Vibration Detection
We will learn to be alert by LED lights if there is a vibration.
# Components and supplies:
- vibration sensor 
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/120.jpg)
- Arduino
- Green and red led lights
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/124.jpg)

- Jumper wires
# Wiring to an Arduino:
To wire the vibration sensor to the Arduino simply connect the following as
shown:
Sensor connection :
- VCC -> 5V
- GND -> GND 
- D0 -> D2
LED connection : 
- positive ( long leg ) -> D13
- negative (short leg ) -> GND

![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/119.jpg)

```python
const int vibrationSensorPin = ---; 
const int ledPin = ---; 
int sensorValue = 0; 
void setup() {
  Serial.begin(9600);
  pinMode(vibrationSensorPin, ---);
  pinMode(ledPin, ---);
  Serial.println("Vibration sensor and LED test initialized.");
}
void loop() {
  sensorValue = digitalRead(vibrationSensorPin);
  Serial.print("Vibration Sensor Value: ");
  Serial.println(sensorValue);
  if (sensorValue == ---) {
    digitalWrite(ledPin, HIGH); 
  } else {
    digitalWrite(ledPin, LOW);
  }
  delay(1000);
}
```
## 4- Make a siren 

We will learn how to use button controlled siren with different LED transi-
tions.
# Components and supplies:
 - Arduino
 - Buzzer
 - Resistor 221 ohm
 - Jumper wires
 - Breadboard
 - Led light (green and red)

# Wiring to an Arduino:
To wire the LED light and resistors to the Arduino simply connect the following as shown:
buzzer connection :
- positive leg -> D8
- negative leg -> 220 ohm-> GND
led connection :
- short leg -> 220 ohm -> GND
- long leg -> D13

![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/114.jpg)

```python
int i; // defines the variable "i" used in a for loop
void setup ()
{
  pinMode (---, OUTPUT); // define port 7 as an output port
  pinMode (---, OUTPUT); // define port 4 as an output port
}
void loop ()
{
  for (i = 0; i <350; i ++) // defines the duration of the first sound (350 cycles of 2 milliseconds).
    // The extended description of the use of the for statement can be found
    // in operation 05 - carousel of lights
  {
    digitalWrite (---, HIGH); // activate the sound
    digitalWrite (---, HIGH); // turn on the led
    delay (1); // wait 1 millisecond. In fact it repeats the sound every 2 milliseconds e
    // therefore with a frequency of 500 repetitions per second
    digitalWrite (---, LOW); // turn off the sound
    delay (1); // wait 1 millisecond and restart from the for statement (350 repetitions)
  }
  delay (50); // wait 50 milliseconds before launching the second sound cycle
  for (i = 0; i <150; i ++) // defines the duration of the second sound (150 cycles of 4 milliseconds)
  {
    digitalWrite (---, HIGH); // activate the sound
    digitalWrite (---, LOW); // turn off the led
    delay (2); // wait 2 milliseconds (repeats the sound every 4 milliseconds and then
    // 250 times per second)
    digitalWrite (---, LOW); // turn off the sound
    delay (2); // wait 2 milliseconds and repeat the cycle 150 times
  }
}
```

## 5- Blinking LED using Arduino and Push button switch
we will learn how to turn on and turn off the LED light using Push button switch.
# Components and supplies:
- Arduino UNO
- Pushbutton switch
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/117.jpg)

- Resistor 220 ohm
- Breadboard
- Jumper wires
- LED Light
# Wiring to an Arduino:
Please follow the diagram.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/112.jpg)

```python
int led1 =2;
int led2 =3;
int led3 =5;
int button =6;
--- setup () {
pinMode ( button , --- );
pinMode ( led1 , --- );
pinMode ( led2 , --- );
pinMode ( led3 , --- );
}
void loop () {
int ButtonStatus = --- ( button );
if ( ButtonStatus == HIGH )
{
digitalWrite ( led1 , --- );
digitalWrite ( --- , HIGH );
digitalWrite ( --- , HIGH );
} else {
digitalWrite ( led1 , LOW );
digitalWrite ( led2 , ---);
digitalWrite ( led3 , LOW );
}
}
```
# 6- Ultrasonic sensor using Arduino and LED light
we will learn how to turn on and turn off the LED light using ultrasonic sensor regarding to distance detection.

# components and supplies: 
- Arduino UNO
- resistor 220 ohm
- LED light
- Jumper wires
- Ultrasonic sensor
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/111.jpg)

# Wiring to an Arduino: 
please follow the diagram.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/18.jpg)
```python
const int trigPin = 9; 
const int echoPin = 10; 
const int ledPin = 13; 
void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(ledPin, OUTPUT);
}
void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  long duration = pulseIn(echoPin, HIGH);
  long distance = duration * 0.034 / 2;
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  if (distance < 20) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
  delay(1000);
}
```
# 7- Servo motor using ultrasonic sensor and Arduino 
will will learn how to turn on the servo motor regarding to distance detection by ultrasonic sensor.
# Components and supplies: 
- Arduino UNO
- ultrasonice sensor 
- servo motor
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/13.jpg)
- jumper wires
- breadboard
# Wiring to an Arduino: 
please follow the diagram.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/new_images/15.jpg)
```python
#include <Servo.h>
const int trigPin = 9; 
const int echoPin = 10; 
const int servoPin = 11; 
Servo myServo;
void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  myServo.attach(servoPin);
}
void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  long duration = pulseIn(echoPin, HIGH);
  long distance = duration * 0.034 / 2;
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  if (distance < 20) {
    myServo.write(90); 
  } else {
    myServo.write(0); 
  }
  delay(1000);
}
```


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
