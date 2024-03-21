#### Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
###  DATE: 21/3/2024
###  NAME: NARESH.PS
###  ROLL NO :212223040127
###  DEPARTMENT:CSE

### AIM :
To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

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

### PRGORAM
```
int en=6;
int in1=3;
int in2=4;

void setup()
{
  pinMode(en , OUTPUT);
  pinMode(in1 , OUTPUT);
  pinMode(in2 , OUTPUT);
}

void loop()
{
  analogWrite(en, 100);
  delay(1000); 
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  delay(1000);
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
}
```
### OUTPUT
CIRCUIT DIAGRAM:
![315062109-3135daa1-b9e2-4227-9b9a-159e8625e253](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/155141830/981895cd-07e1-4350-bf03-9185390da974)

SCHEMATIC DIAGRAM:
![315062262-5584da42-9931-43dc-8098-af0ea67b26c9](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/155141830/081ec65e-e745-4cde-bee7-0d457a30c963)

### GRAPH AND TABULATION 
![315062372-5630056f-f16b-44b7-8aa1-9bbe7ed57fca](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/155141830/d8276e3f-3d10-4903-a77e-6241103cf046)


![315062597-d495b501-e0cf-4cab-ac85-50f7fc473818](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/155141830/46c2f2c6-00ac-44c3-8f0a-94525da4a5f5)




### RESULTS 
The program to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is completed and executed successfully.


