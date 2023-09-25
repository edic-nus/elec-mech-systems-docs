# How do machines "see"?
Sensors are what enables a machine to figure out the environment around it. Without them, they are essentially blind. 

Although computer vision is prevalent in modern tech, inferred information from computer vision models are nearly always supplemented with data from "single-source" sensors. For example, we can classifiy distance sensors as single-source, as their primary goal is to measure distance. Rotary encoders are another example of this, helping the machine determine how much something has rotated. 

More complex purposes, such as determining the orientation of an object in space, uses a combination of multiple sensors. This is what an IMU (Inertial Measurement Unit) does, a combination of an accelerometer, gyroscope and sometimes a magnetometer. Using the readings from these 3 sensors and some clever mathematics, we can determine the pitch, yaw and roll of an object in 3D space. This [video](https://www.youtube.com/watch?v=eqZgxR6eRjo) is helpful in understanding how this is accomplished. 

## Picking a sensor
Unsurprisingly, different sensors work using different principals and are manufactured by a variety of vendors. Each sensor should always come with a datasheet, detailing how to wire up the sensor, what operating conditions they function in, how to get data out of it, and sometimes even how they work! 

A big factor behind choosing a specific sensor is in-fact the documentation supporting it. This can include datasheets, user manuals, application notes, videos, and even example code. You can have the "best" sensor in the world, but if you don't know how to use it, it's just a paperweight. 

When looking for a sensor to accomplish a certain task, start by researching how other people have accomplished the same task. Spend time learning why they chose sensors and how they work. 

> This is an important step! If you don't build up your own repository of knowledge, you will always be reliant on others to figure out the hard stuff for you. 

Sensors are interfaced with a variety of communication protocls. We will cover a foundational communication protocol in ["Signal lines"](./signal_lines.md). For now, just be aware that there needs to be a method for your machine to communicate with the sensors you have chosen. 

To summarise, ask the following questions when picking a sensor: 
- What type of data is needed? 
- How have others acquired this data? 
- How accurate does the data need to be? 
- What are the different sensors capable of providing this data? 
- Does the sensor provide the data needed directly? If not, what computation is required?
- What is the interface of the sensor? 
- How is the sensor powered? 
- How should the sensor be mounted? 
