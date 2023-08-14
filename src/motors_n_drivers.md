# Motors go brrr
There's a lot of different types of motors with their own list of features. 

When picking a motor, the following questions are usually asked: 
- Do I want my motor to spin continuously or move to a specific position? 
- How precisely does the motor need to move? 
- How strong does my motor need to be (torque)? 
- How fast does my motor need to spin (rpm)?
- How big is the motor (physical size)? 

> These criteria are assuming we are looking for a motor which applies force in the rotational axis. A linear actuator (which is also a motor) would apply force along it's axis

Extracting the first 4 criteria, we can create a rough guideline to pick an appropriate motor:

Criteria/Motor | Positional Servo | Continuos Servo| Geared DC | Normal DC | Brushless DC | Stepper
---|---|---|---|---|---|---
Positional?  | Yes | No | No     | No    | Both  | Both 
Precision?   | Yes | No | Maybe  | No    | Yes   | Yes 
High torque? | Yes | No | Yes    | Maybe | Maybe | No
High RPM?    | No  | No | No     | Maybe | Maybe | No

> If you want to positionally control a continuously rotating motor, you will need some way to keep track of the motors rotation. This can be done using a [rotary encoder](https://en.wikipedia.org/wiki/Rotary_encoder).

Finally, the type of motor also decides what kind of motor driver you will be using. Smaller servos usually don't require any motor driver, while DC motors, stepper motors and brushless DC motors require their own unique drivers. To understand the type of motor driver required, it is good to understand how these different motors function in the first place! When it comes to this, YouTube and Google are your friend. 
