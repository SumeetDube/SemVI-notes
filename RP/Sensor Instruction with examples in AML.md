Define Sensor Instruction. Explain any four sensor instructions with
examples used in AML


**Sensor Instruction**

A sensor instruction is a command or instruction used in AML (A Manufacturing Language) to interact with and configure sensors. These instructions allow users to read sensor data, monitor sensor behavior, and control sensor settings.

**Six Sensor Instructions with Examples**

1. **SENSOR**

The SENSOR instruction is used to read the values of one or more sensors and store them in variables.

Example:
```
SENSOR (<1,2,3>,<10,20,30>);
```
This example reads the values of sensors 1, 2, and 3, and stores them in variables 10, 20, and 30, respectively.

2. **MONITOR**

The MONITOR instruction is used to continuously monitor a sensor and perform an action when a specific condition is met.

Example:
```
MONITOR (SENSOR, 1, 0, 0, 1.5, 'passed');
```
This example sets up a monitor for the sensor device on channel 1. When the sensor device is in state 0 for 1.5 seconds, it will display the message "passed".

3. **WAITSENSOR**

The WAITSENSOR instruction is used to pause the program execution until a specific sensor reaches a desired state.

Example:
```
WAITSENSOR (1, 0, 1.5);
```
This example waits for sensor 1 to reach state 0 for 1.5 seconds. If the sensor reaches the state within the timeout, the program will continue executing.

4. **TESTSENSOR**

The TESTSENSOR instruction is used to test a sensor for a specific state and display a message if the test passes.

Example:
```
TESTSENSOR (1, 0, 'passed');
```
This example tests sensor 1 for state 0. If the sensor is in state 0, it will display the message "passed".

5. **SENSE**

The SENSE instruction is used to sense the state of a sensor and perform an action based on the sensed state.

Example:
```
SENSE (1, 0, MOVE(ARM, fgoal, LED));
```
This example senses the state of sensor 1. If the sensor is in state 0, it will move the ARM device to the fgoal position and turn on the LED.

6. **SENSEWAIT**

The SENSEWAIT instruction is used to wait for a sensor to reach a specific state before continuing program execution.

Example:
```
SENSEWAIT (1, 0, 1.5);
```
This example waits for sensor 1 to reach state 0 for 1.5 seconds. If the sensor reaches the state within the timeout, the program will continue executing.

These sensor instructions in AML enable users to interact with and configure sensors in a variety of ways, allowing for efficient and effective monitoring and control of manufacturing processes.