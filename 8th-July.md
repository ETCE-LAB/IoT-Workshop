# IoT workshop Exercises 


[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Lets just start :)
# Have fun!

# 1. Motion Detection with PIR sensor
This sensor is a PIR (Passive Infrared) sensor. PIR sensors are used for motion detection and are widely used in security systems, automatic lighting, and other devices. The specially designed front lens of the sensor focuses on infrared radiation from moving objects.

# Components and supplies:
- PIR sensor
-![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0133.jpg)
- Arduino UNO
- LED lights
- Resistor 220 ohm
- Jumper wires
- Breadboard

# Wiring to an arduino: To wire the flame sensor to the arduino simply connect the following as shown:
# Sensor connection:
- vcc -> 5v 
- GND -> GND
- OUT -> D2
# LED connection
- Long leg of LED -> D13
- Short leg of LED -> Resistor 220 ohm
- Resistor 220 ohm -> GND
NOTE : PIR sensors usually require time to calibrate. This time can be a few seconds to a few minutes.
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0116.jpg)

# 2. Color Detection with TCS3200 sensor
This is a TCS3200 colour sensor. The TCS3200 is a colour detection sensor that can detect different colours using colour photodiodes (red, green, blue and transparent). This sensor is usually used in robotics and electronic projects to detect the colour of objects.
# Components and supplies:
- TCS3200 sensor
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0103.jpg)
- Arduino UNO
- Jumper wires
# Wiring to an arduino: To wire the flame sensor to the arduino simply connect the following as shown:
- vcc -> 5v
- GND -> GND
- S0 -> D4
- S1 -> D5
- S2 -> D6
- S3 -> D7
- OUT -> D8
- LED -> D9
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0114.jpg)

# 3. Smart Street Light using LDR
This piece is an LDR (Light Dependent Resistor) or photocell. LDR is a light resistor whose resistance value changes according to the amount of light shining on it. In other words, as the light intensity increases, the LDR resistance decreases, and its resistance increases as the light intensity decreases. This feature makes the LDR suitable for use in light measurement projects.

# Components and supplies:
- LDR, 5 Mohm
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0127.jpg)
- Arduino UNO
- Jumper wires
- 2 Resistor 220 ohm 
- LED light

# Wiring to an arduino: To wire the flame sensor to the arduino simply connect the following as shown:

- one leg of LDR -> v5
- another leg of LDR -> A2 and resistor 220
- resistor 220 -> GND
Note: You already know the connection of LED to the arduino ;) 
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0123.jpg)
# 4. Security System with Ultrasonic sensor
You already know what the ultrasonic sensor is ;) 
# Components and supplies:
- Ultrasonic sensor
- Buzzer
- Arduino UNO
- 3 LED lights (Green, Yellow, Red )
- 3 resistor 220 ohm
- Jumper wires
- Breadboard

# Wiring to an arduino: To wire the flame sensor to the arduino simply connect the following as shown:
# sensor to arduino
- vcc -> 5v
- GND -> GND
- Trig -> D9
- Echo -> D10
# buzzer to arduino
- +ve leg -> D8
- -ve leg -> GND
# LED light to arduino
- long leg of green led -> D2
- long leg of yellow led -> D3
- long leg of red led -> D4
- short leg of all led's -> resistor 220 ohm
- resistor 220 ohm -> GND
![Alt Text](https://github.com/ETCE-LAB/IoT-Workshop/raw/main/images/0118.jpg)




