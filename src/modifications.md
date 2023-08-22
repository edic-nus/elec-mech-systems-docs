# System architecture 
![detailed_bot_image](./img/detailed_bot.png)

There are 3 major changes in the system architecture: 
- Number of motor drivers 
- Two different voltage (power) lines 
- Two different signal lines 

The number of motor drivers were reduced as the motor driver chosen, the L298N, is capable of driving two motors at once, making a second motor driver redundant. 

A distinction has only been made between voltage lines, with the battery powering the L298N module, the L298N module powering the MCU and the MCU powering the ultrasonic sensor. This is because the battery will output 12 V, while the MCU requires 5 V.

Power flow:
```mermaid
graph LR;
Battery --12V--> L298N
L298N --5V--> MCU 
MCU --5V--> Ultrasonic
```

> The above description is not accurate. The LM7805 linear regulator **on the** L298N motor driver module steps down the 12V voltage to 5V, which is then connected to the microcontrolller. Certain microcontroller **boards** also have linear regulators on board, allowing them to accept 12V directly. 

> The distinction between board and IC (Integrated Circuit) is important as a board can hold multiple chips, including linear regulators.

Finally, the signal lines have been broken down into GPIO(General Purpose Input Output) and PWM(Pulse Width Modulation). The distinction is important as most MCUs have PWM pins limited to a few pins on the board. The extra information provided by this diagram would allow them to build their circuits without having to comb through the datasheets of both the MCU and the L298N module. 

> GPIO pins in this case refer to pins which have been configured for normal/non-unique input and output tasks. 
