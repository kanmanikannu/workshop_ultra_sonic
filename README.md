#                                        WORKSHOP

## AIM:
   Display the readings of ultrasonic using ESP32.

## COMPONENTS REQUIRED:
  ESP32,HC-SR04,LCD 16X2,Jumpers.

## Theory:
### HC-SR04
   The HC-SR04 ultrasonic sensor is a key component in many IoT projects, particularly for distance measurement. This sensor operates by emitting ultrasonic waves using its transmitter and then receiving the echoes with its receiver. When a trigger pulse is sent, the sensor emits a burst of ultrasonic waves, and upon hitting an object, these waves bounce back and are detected by the receiver. By measuring the time taken for the waves to travel to the object and back, the sensor calculates the distance using the speed of sound in the air. This distance calculation, based on the time difference between the trigger pulse and the received echo, is then used for various IoT applications such as proximity sensing, obstacle detection, or environmental monitoring. Understanding this theory is crucial for effectively utilizing the HC-SR04 sensor in IoT projects, enabling accurate distance measurements and informed decision-making based on detected objects or proximity.

### LCD 16X2
  The LCD 16x2 display is often used in conjunction with ultrasonic sensors like the HC-SR04 in IoT projects to provide real-time distance readings or other relevant information. The theory behind integrating these components involves several steps:

Firstly, the HC-SR04 ultrasonic sensor sends out ultrasonic waves and receives the echoes to measure distances, as explained earlier. Once the distance measurement is obtained, this data is sent to a microcontroller like Arduino, which processes the information.

Next, to display this data on the LCD 16x2 screen, the microcontroller communicates with the LCD using the LiquidCrystal library. The library allows for easy control of the LCD's functions, such as displaying text, moving the cursor, or clearing the screen.

## ESP32
  The ESP32 microcontroller is a versatile and powerful component often used in IoT projects, including those involving ultrasonic sensors like the HC-SR04. Integrating the ESP32 with an ultrasonic sensor involves several steps:

Firstly, the ESP32 is programmed using Arduino IDE or other compatible development environments. This programming includes setting up GPIO pins to interface with the ultrasonic sensor. For example, one GPIO pin can be used as a trigger pin to send the ultrasonic signal, while another GPIO pin is used as an echo pin to receive the reflected signal.

When the ESP32 triggers the ultrasonic sensor by sending a high signal through the trigger pin, the sensor emits an ultrasonic wave burst. This burst travels through the air until it encounters an object, where it reflects back to the sensor.

The ESP32 then listens for the echo signal on the echo pin. By measuring the time it takes for the echo to return, the ESP32 calculates the distance to the object using the speed of sound in the air (approximately 343 meters per second).

## PROGRAM:
```
#include <LiquidCrystal.h>

int rs=9;

int en=8;

int d4-2;

int d5-3;

int d6-4;

int d7-5;

LiquidCrystal lcd(rs,en,d4, d5, d6, d7);

int trig-1;

int echo =0;

void setup() {

// put your setup code here, to run once:

lcd.begin(16,2);

pinMode (trig, OUTPUT);

pinMode (echo, INPUT);

Serial.begin(9600);

void loop(){

// put your main code here, to run repeatedly lcd.setCursor(0,1);

digitalWrite(trig, LOW); delay(1000); digitalWrite(trig, HIGH); delay (2000); digitalWrite(trig,LOW);

delay (2000);

int time pulseIn (echo, HIGH); lcd.println(time); //time in microsecond float distance lcd.setCursor(1,0); (time*0.034)/2; //speed in cm lcd.print("distance"); lcd.printin (distance);

lcd.print("cm");

delay(1000);
}
```
## CIRCUIT DIAGRAM:
![image](https://github.com/kanmanikannu/workshop_ultra_sonic/assets/114866367/a1d05d44-b125-425b-a068-38ba22042378)

## OUTPUT:
![image](https://github.com/kanmanikannu/workshop_ultra_sonic/assets/114866367/ac54b01f-64c8-4369-a3ea-4f2072fbe594)

## RESULT:
  The circuit is verified and thus the result is obtained

