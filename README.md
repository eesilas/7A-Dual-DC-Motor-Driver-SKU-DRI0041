# 7A-Dual-DC-Motor-Driver-SKU-DRI0041
Control remora brush motors

SKU:DRI0041
Introduction
DRI0041 2x7A DC Motor Driver

This is an ultra small dual DC motor driver for space limited projects. It features a UVLO (Under Voltage Lock Out) circuit, ESD protection, and opto-isolated inputs. The opto-isolated inputs prevent motor power from damaging or interfering with your control circuit.

Specification
DRI0041 2x7A DC Motor Driver Specification
Voltage supply: DC 7 ~ 24 V
Voltage supply limit: 6.5 ~ 27 V
Control signal Level (Compatible 3.3V/5V)
High: DC 3.0 ~ 6.5 V
Low: DC0 ~ 0.8 V
Output Channels: 2
Control signal current: 3 ~ 11 mA (per input)
Maximum continuous operating current: 7 A
Peak current: 50 A
Speed control: PWM
Minimum valid Pulse Width: 5 us
Working Temperature: -25 ~ 85 °C
Mounting Hole: M3
Dimension (Length * Width * Height): 55 x 55(mm)/2.165 x 2.165(in)
Weight: 32g
Board Overview
DRI0041 2x7A DC Motor Driver Board Overview
Num	Label	Description
1	9 - 24V	Power Supply, +
2	PGND	Power Supply, GND
3	OUT1	Motor1_+
4	OUT2	Motor1_-
5	OUT3	Motor2_+
6	OUT4	Motor2_-
7	ENA	Motor1 PWM
8	IN1	Motor1 control signal
9	IN2	Motor1 control signal
10	ENB	Motor2 PWM
11	IN3	Motor2 control signal
12	IN4	Motor2 control signal
13	+5V	Voltage Reference Input, +5V OR 3.3V
Control Method

IN1	IN2	ENA/ ENB	Motor1/2 Behavior
0	0	x	Stop (brake)
1	1	x	Vacant
1	0	1	Forward 100%
0	1	1	Reverse 100%
1	0	PWM	Forward at PWM speed
0	1	PWM	Reverse at PWM speed
In this table

IN1 & IN2: the control signal input to change the motor behavior
"0": TTL_Low
"1": TTL_High
"x": Any TTL, and it is default TTL_Low while no PWM signal.
"ENA/ ENB": PWM speed setting
Note:

IN1 & IN2

To protect your motor, before switching the motor drive direction, first BRAKE the motor by setting IN1=0 & IN2=0. This is especially important when the PWM is set to 100% (full speed). The suggested braking time is >0.1sec, depending on your motor.

+5V

This signal is a reference that must be set to the same power supply that your microcontroller operates on. Connect this to the 3.3v or 5v power supply used by the controller.

Tutorial
This tutorial will cover how to use PWM to control a motor using the shield. Do the wiring according to the Connection Diagram below, and then upload the sample code below to the Arduino board. Here we use a arduino UNO as the controller, you should see your motor run forward for 3 seconds and then run reverse for another 3 seconds and then repeat.

Requirements
Hardware

1 x DFRduino UNO (or similar)
1 x This 7A Dual DC Motor Driver
2 x DC Motor
1 x Fuse@20A
Jumper wires
Software

Arduino IDE Click to Download Arduino IDE from Arduino®.
Connection Diagram
DRI0041 2x7A DC Motor Driver Connection Diagram DRI0041 2x7A DC Motor Driver Connection Diagram
Facility Safety and the Personal Safety:
Please add a fuse@20A between the Power source and this shield.

Installation Tips

The back of the driver board has some large bare traces. It is important to make sure that these do not get shorted out against conductive surfaces of your project. Please measure carefully and if needed, apply 1mm of non-conductive epoxy to protect the board.

Pluggable Connector

The connectors are designed to be pluggable. This allows you to attach wires with male or female terminations.

DRI0041 2x7A DC Motor Driver Connection Diagram

Mega 2560 Pro control 2 Motor Drivers
Key Features:
Extended to 4 Motors: Uses two DRI0041 motor drivers (each controlling 2 motors)
Individual Control: Each motor has its own set of control functions (forward, backward, brake)
Group Control: Convenience functions to control all motors simultaneously
Test Sequence: Demonstrates both individual and group motor control
PWM Speed Control: All motors support variable speed control
Pin Configuration:
First Motor Driver (Motors 1 & 2):

Motor 1: IN1(5), IN2(4), ENA(6)
Motor 2: IN3(8), IN4(7), ENB(9)
Second Motor Driver (Motors 3 & 4):

Motor 3: IN5(22), IN6(23), ENC(24)
Motor 4: IN7(25), IN8(26), END(27)
You can modify the pin assignments as needed for your specific wiring configuration. The program includes a test sequence that demonstrates all motor functions.
