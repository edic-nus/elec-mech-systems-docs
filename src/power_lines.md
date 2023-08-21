# More powerrr 
As shown in the example system, the devices in your system can function at varying voltage levels. In the context of digital devices, we refer to the level the device runs as the **logic level**. For example, the STM32F103 runs at a logic level of 3.3V. However, it is capable of accepting voltages of up to 5V on its voltage input pin. 

When designing a system, care should be taken to note down the different voltages at present and highlight areas where voltage step-up or step-down is needed. 

## Stepping voltage up or down 
Buck converters can be used to step-down voltage while boost converters can be used to step-up voltage. 

Linear regulators can are also capable of stepping-down voltage, but they are more in-efficient than buck converters due to how they function. However, LDO(low-dropout) regulators, a type of linear regulator, has the special function of maintaining the output voltage even when the input voltage is very close to the output voltage. This characteristic of LDOs make it desirable in certain circuits. 

### Shifting logic level
When connecting the communication lines of two devices with different logic levels, a logic level shifter **might** be required. The need for one can be discerned by combing through the datasheets for both devices to find the voltage level where "ON" and "OFF" states are registered. Additionally, certain 3.3 V devices have 5 V tolerant pins, allowing you to at least have one-way communication from the 5 V device to the 3.3 V device without any additional hardware. 



