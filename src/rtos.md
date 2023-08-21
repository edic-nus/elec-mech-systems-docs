# while(1) 
In a normal microcontroller control flow, nearly all of your logic is placed into a single, infinite loop. In a more complex system however, this can result in a critical piece of code not running till all other components have finished running, which can caused certain functions of the system to become sluggish. Additionally, a badly written component of the code has the capability to slow down all other components.

To circumvent this issue, we can use a RTOS (Real Time Operating System).

# What does an RTOS do? 
An RTOS is a type of operating system. Personal computers run general purpose operating systems, such as Windows, MacOS or a Linux-based distribution. While general purpose operating systems are designed to run a variety of different software, an RTOS is desgiend with speed and time sensitivity in mind. 

Instead of arranging your code into a single/super loop, we can break them down into multiple tasks. Each task will have it's own infinite loop. A priority should then be assigned to each task. Using this information, the RTOS will run all the tasks concurrently with the different levels of priority affecting their running time. 

> Concurrent != Parallel. Concurrency involves running multiple tasks on a single processing core, switching between tasks rapidly to give the illusion they are running at the same time. Running tasks in parallel involves running them across multiple cores, resulting in them truly running at the same time. 

Just like general purpose operating systems, there are different implementations of RTOSs, such as FreeRTOS, Zephyr and NuttX. If you would like to know more about a specific implementation or just want to learn more about the other features of RTOSs, do checkout the individual documentations of the above implementations. 
