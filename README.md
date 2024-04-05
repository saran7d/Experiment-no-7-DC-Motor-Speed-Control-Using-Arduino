###  DATE: 05.04.2024

###  NAME: SARAN S S
###  ROLL NO : 212221220048
###  DEPARTMENT: INFORMATION TECHONOLGY
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```c

int in1=5;
int in2=6;
int en=3;;

void setup()
{
  pinMode(in1, OUTPUT);
   pinMode(in2, OUTPUT);
   pinMode(en, OUTPUT);
}

void loop()
{ 
  analogWrite(en,50);
  
  digitalWrite(in1, HIGH);
   digitalWrite(in2, LOW);
  delay(5000);
  
}


```
## OUTPUT:
### CIRCIUT
![Screenshot 2024-04-05 160053](https://github.com/saran7d/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/104412179/780f3961-5429-4c8a-bdee-f65c10af0e12)


### SCHEMATIC DIAGRAM
![Screenshot 2024-04-05 160108](https://github.com/saran7d/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/104412179/0c0e05d1-9406-486d-94fd-c8f04bd04829)

### GRAPH AND TABULATION 
![EXP 6 GRAPH](https://github.com/saran7d/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/104412179/ff0dba67-db71-4326-864c-2e64a42e1d16)
![EXP 6 TABLE](https://github.com/saran7d/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/104412179/7f34e1fe-097d-4969-9024-064f83775564)


### RESULTS AND DISCUSSION 
Thus, the speed and the direction of a DC motor using L293D driver ic(H- bridge) is controlled.
