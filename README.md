# Camera_Gimbal_Control_Board_Prototype
Prototype PCB designed in Altium 19 to act as a shield to an STM32F303RE Nucleo Board, providing a power management system, motor drivers, and custom headers.

## System Requirements
The system requirements are subdivided into the following sections:
  - Interface requirements (Port and Pin Configurations)
  - Electrical requirements
  
### Interface Requirements
The shield requires the following connectors.
I/O Connectors:
  - 2 x 38 pin header to interface with the STM Nucleo board. 
  - 3 x 4 pin I2C Connector for Motor Encoder I/O                     (3.3V, GND, SDA, SCL)
  - 2 x 5 pin I2C Connector for 9-axis IMU I/O                        (3.3V, GND, SDA, SCL, IMU_Interrupt)
  - 3 x 3pin RC connectors (passing RC signals to the STM)            (5.0V, GND, RC_Signal)
Power and I/O Connectors:
  - 1 x 4 pin I/O Coprocessor (Raspberry Pi 3B+) and power connectors (5.0V, GND, UART_RX, UART_TX) 
Power:
  - 3 x 3 pin Motor phase connector                                    (Phase A, Phase B, Phase C)
  - 1 x 2 pin XT60 Input battery connector                             (VBatt, GND)
  
### Electrical Requirements
  - Input Voltage: 6S LiPo Battery: 18V to 25.2V
  - Output Voltage Rail 1: 12V at 8A for: Motor Driving (Max 2.5A per motor)
  - Output Voltage Rail 2: 5V  at 5A for: STM32F303RE Nucleo (500mA), Raspberry Pi 3B+ (1A), RC Radio Receiver (1A)
  
Load currents were estimated, so an additional requirement is adding a current monitor to the 12V and 5V rails is required to better design the power management system for the final design.
