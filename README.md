IOT BASED RAIN DETECTION SYSTEM



A Project Report

In the partial fulfillment for the award of the degree of 

B.Tech


under

Ardent Computech Pvt. Ltd.


 
Submitted by

Suman Purkait


 

Netaji Subhash Engineering College


Certificate from the Mentor

This is to certify that Suman Purkait has successfully completed the project titled “IOT BASED RAIN DETECTION SYSTEM” under my supervision during the period from February to May which is in partial fulfillment of requirements for the award of the B.Tech and submitted to Department Electronics and Communications Engineering of Netaji Subhash Engineering College.





                                                                                                      ____________________
  Signature of the Mentor



Date:19.09.2021



Acknowledgement


I take this opportunity to express my deep gratitude and sincerest thanks to my project mentor, Shouvik Sarkar and Tathagata chatterjee for giving the most valuable suggestion, helpful guidance and encouragement in the execution of this project work.

I would like to give a special mention to my colleagues. Last but not the least I am grateful to all the faculty members of Academy of Skill Development for their support.



























DECLARATION

We hereby declare that the project work being presented in the project proposal entitled “IOT BASED RAIN DETECTION SYSTEM” in partial fulfilment of the requirements for the award of the degree of BACHELOR OF TECHNOLOGY IN
ECE at ARDENT COMPUTECH PVT. LTD, SALTLAKE, KOLKATA, WEST BENGAL, is an authentic work carried out under the guidance of  Shouvik Sarkar and Tathagata chatterjee. The matter embodied in this project work has not been submitted elsewhere for the award of any degree of our knowledge and belief.


Date: 18.09.2021



Name of the Students

1.	Suman Purkait
2.	Ranadeep Pain
3.	Rounak Banerjee
4.	Rabisha Jaiswal


Signature of the students

1.   
2.  
3.   
4.  


 
                         Ardent Computech Pvt Ltd (An ISO 9001:2015 Certified)
Module 132, SDF Building, Sector 5, Salt Lake, Kolkata - 64

CERTIFICATE

This is to certify that this proposal of minor project entitled “IOT BASED RAIN DETECTION SYSTEM” is a record of bona fide work, carried out by SUMAN PURKAIT under my guidance at ARDENT COMPUTECH PVT LTD. In my opinion, the report in its present form is in partial fulfilment of the requirements for the award of the degree of BACHELOR OF TECHNOLOGY IN ELECTRONICS AND COMMUNICATION ENGINEERING and as per regulations of the ARDENT®. To the best of my knowledge, the results embodied in this report, are original in nature and worthy of incorporation in the present version of the report.

Guide / Supervisor
_____________________________________________________________
[Shouvik Sarkar and Tathagata chatterjee]
          Ardent Computech Pvt Ltd (An ISO 9001:2015 Certified)
Module 132, SDF Building, Sector 5, Salt Lake, Kolkata - 64
 

PROJECT OBJECTIVE

Water managed from rainfall aims to reduce economic impact and risk of lives. Most developing countries depend on rainfall for their water needs. However with poor management of rainfall water, it is difficult for example to determine water losses to evaporation or ground water recharge, how much is still available etc. Therefore rainfall measurement and monitoring is an important factor when it comes to water management as this determines the current rainfall and future prediction of rainfall hence leading to better management of water. Rainfall measurement devices like rain gauges have been a useful tool in the weather monitoring systems for a very long time. Since a rain gauge was one of the devices that were proven to be beneficial, particularly to agriculture, the rain gauge system has been improved as technology advanced. In the water control and management systems for example, these sensors can be used to help obtain and process information such as rainfall, soil moisture, and soil temperature over large geographical areas. The network uses a tipping bucket rain gauge (TBRG), temperatures and humidity sensors, GPRS module and a micro-controller to relay rainfall data to a remote server, while a solar panel is used to convene energy to critical components of the wireless sensor network.

















INDEX

1. PROJECT COMPONENT LIST
2. DESCRIPTION OF EACH COMPONENT
3. PROJECT DISCUSSION
4. PROJECT STEPS
5. PROJECT PICTURE
6 .PROJECT CIRCUIT DIAGRAM
7. RESULT
8. CONCLUSION

























PROJECT COMPONENT LIST

1. Nodemcu board x 1 
2. Rain sensor x 1
3. LED x1
4. Resistor 1k ohm
5. Breadboard x 1 
6. Jumper wires


























DESCRIPTION OF EACH COMPONENT

Nodemcu board:-  NodeMCU is an open source firmware for which open source prototyping board designs are available. The name "NodeMCU" combines "node" and "MCU" (micro-controller unit). The firmware uses the Lua scripting language. The firmware is based on the eLua project, and built on the Espressif Non-OS SDK for ESP8266.
 
ESP8266 Nodemcu
Rain sensor:- A rain sensor or rain switch is a switching device activated by rainfall. There are two main applications for rain sensors. The first is a water conservation device connected to an automatic irrigation system that causes the system to shut down in the event of rainfall.
 
Rain sensor



LED: A light-emitting diode (LED) is a semiconductor light source that emits light when current flows through it. Electrons in the semiconductor recombine with electron holes, releasing energy in the form of photons.
 
LED

Resistor :  A resistor is a passive two-terminal electrical component that implements electrical resistance as a circuit element. In electronic circuits, resistors are used to reduce current flow, adjust signal levels, to divide voltages, bias active elements, and terminate transmission lines, among other uses.   
 
Resistor





Breadboard: A thin plastic board used to hold electronic components (transistors, resistors, chips, etc.) that are wired together. Used to develop prototypes of electronic circuits, breadboards can be reused for future jobs. They can be used to create one-of-a-kind systems but rarely become commercial products.
 
Breadboard


Jumper wires: Jumper wires are simply wires that have connector pins at each end, allowing them to be used to connect two points to each other without soldering. Jumper wires are typically used with breadboards and other prototyping tools in order to make it easy to change a circuit as needed. Fairly simple.
 
Jumper wires







PROJECT DISCUSSION

In this project we'll see how to Interface raindrop sensor to NodeMcu and get alarm whenever the rain intensity crosses some threshold. It can be used as a switch when raindrop falls through the raining board and also for measuring rainfall intensity. The module features, a rain board and the control board that is separate for more convenience, power indicator LED and an adjustable sensitivity though a potentiometer.
Raindrop sensor is basically a board on which nickel is coated in the form of lines. It works on the principal of resistance. When there is no rain drop on board. Resistance is high so we gets high voltage according to V=IR. When rain drop present it reduces the resistance because water is conductor of electricity and presence of water connects nickel lines in parallel so reduced resistance and reduced voltage drop across it.













PROJECT STEPS
Step 1
Firstly, identify these components.
  
                   ESP8266 Nodemcu                              Rain sensor

  
                            LED                                       Breadboard                            
                          Jumper wires

Step 2
Secondly, connect these components. To do this, use the circuit diagram below.
 
Step 3
Thirdly, we set up the Thingspeak app. To do this, follow the steps below.
•	First, go to the Thingspeak website and create a new account using my email address. Then, click the “New channel” button.
 
 
 
Next, enter my project name as my like. Then, activate the four fields and name “Rain_level”. After, click the “Save channel” button.
 
  
•	So, now we can see the interface of this project.
 
Step 4
Now, let’s create the program for this project. It is as follows.
•	WI-Fi library — Download
Code:
#include "ThingSpeak.h"
#include <ESP8266WiFi.h>

const char* ssid     = "CHATTERJEE HOUSE";
const char* password = "Tatha@1234";
const char* server="api.thingspeak.com";
int status = WL_IDLE_STATUS;

unsigned long channel =1510198;
unsigned int soil = 1;
const char* APIkey = "I3XEJVKB9JMRQK3T";

WiFiClient  client;

void setup() 
{
  Serial.begin(9600);  
  pinMode(A0, INPUT);
  WiFi.begin(ssid, password);
  ThingSpeak.begin(client);
  Serial.begin(9600);
}

void loop() 
{
  int sensor = analogRead(A0);
  
  Serial.println(sensor);

  ThingSpeak.setField(1, sensor);
  ThingSpeak.writeField(channel, 1, sensor, APIkey);
  Delay(5000);
}







Step 6
Now, go back to the Thingspeak app and click the private view tab. 
 
 


PROJECT PICTURE
 


PROJECT CIRCUIT DIAGRAM
 





RESULT

This system works in such a way that, when there is rain, the rainwater acts as a trigger, which switches on the buzzer. In the Rain Drop Sensor Arduino Code, we defined that pins 5, and A0 are buzzer and rainfall. By doing this, we can change the pins in the defined part of the function, and the remaining part of the code will be untouched. This will make the programmer in editing the pins easily.
In the void loop, the analogRead command reads the value from the sensor. In the next line, the command Serial.println(value), prints the value on the serial monitor. This will be helpful while debugging. The map function maps the incoming value between 0 -225. The function format for the map is a map (value, min value, maximum value, value to be mapped for minimum value, value to be mapped for maximum value). The buzzer will be switched ON or OFF, depending on the set value and the output of the sensor. This value is compared if function, with the set value. If the value is greater than the set value, it will switch on the buzzer. If the value is less than the set value, the buzzer will be switched off.



















CONCLUSION

A simple Rain Detection System can be easily built by interfacing an Arduino with Rain Sensor. The sensor will detect any rainfall falling on it and the Arduino board will sense it and can perform required actions. A system like this can be used in many different fields, such as agriculture and automobile fields. Rainfall detection can be used to automatically regulate the Irrigation process. Also, continuous rainfall data can help farmers use this smart system to automatically water the crop only when absolutely required. Similarly, in the automobiles sector windshield wipers can be made fully automatic by using the rain detection system. And the Home Automation Systems can also use rain detection to automatically close windows and adjust room temperature. In this tutorial, we will build a basic rain sensor using Arduino with a buzzer. You can then use this set-up to build anything you wish on top of it. Also, note that the rain sensor module is also referred to as a raindrop sensor or rain gauge sensor or rainwater sensor based on usage, but they all refer to the same sensor used in this project and they all work on the same principle.
We have also built a simple Rain Alarm and an automatic car wiper by using 555 Timer only, you might want to check that as well if you do not want to use an Arduino.That being said, let’s get back to this project and start building our Arduino Rain Gauge.

REFERENCES

ThingSpeak:https://thingspeak.com/channels/1510198/private_show
Arduino: https://www.arduino.cc
Rain Sensor :https://lastminuteengineers.com/rain-sensor-arduino-tutorial
ESP8266 NodeMCU:https://lastminuteengineers.com/esp8266-nodemcu-arduino-tutorial/



