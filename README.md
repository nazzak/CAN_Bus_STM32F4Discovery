# CAN_Bus_STM32F4Discovery

**This project is still very experimental, proceed at your own risk.**

This project shows how to deal with the CAN peripheral on STM32F4

## 1. Build and Test Environment
Os : Mac os x High Sierra
IDE : System Workbench (SW4STM32) + STM32CubeMX + HAL V1.18.0. 
2 x stm32f4discovery boards and 2 x stm32f4discovery shields. 
2 x USB cables to power and load a program into the target. 

## 2. File organization
- src : the sources or the stm32f4 project.
- inc : the headers or the project.
- Drivers : HAL driver + CMSIS.
- startup : startup file.
- can.ioc : CubeMX file.

## 3. Setup the environment
- Install SW4STM32 and STM32CubeMX.
- Have a look to the STM32CubeMX Project. The source code is generated from STM32CubeMX. 
- Import the entire directory to the SW4STM32
- Build and Run the program on your target.

## 4. Hardware setup
The shield board embed a CAN Bus transceiver SN65HVD230 from Texas Instruments.  
The Pins are connected as below :  
SN65HVD230_D_PIN  <==>  PD1/CAN1-TX  
SN65HVD230_R_PIN  <==>  PD0/CAN1-RX

PA0 is used in interruption mode to send the message over the CAN Bus.  
the state of the LEDs will act according to the message received.  

Connect the 2 bords by their CAN transceiver :  

BORD1_CAN_H  <==>  BORD2_CAN_H  
BORD1_CAN_L  <==>  BORD2_CAN_L

## 5. How to use the software
The software can handle the Std and the Ext message ID.  
Edit the define directive on the line 52 in the main.c  
Don't forget to swap the messages ID between the 2 boards before programming them.  
