i) MONITOR (LED, 2,0,0,1.5, ‘passed’);

MOVE (ARM, fgoal, LED);

ii) ATTN: SUBR;

MOTPARMS: NEW STOPMOVE;

WAITMOVE;

BREAK (EOL, ‘ATTENTION REQUESTED’);

APPLY (‘AMOVE’, MOTPARMS);

END;

iii) DMOVE (<4,5,6>,<30,-60,90>);

iv) SPEED (0.8)


-----------

1. **Example 1:**

```
MONITOR (LED, 2,0,0,1.5, ‘passed’);
MOVE (ARM, fgoal, LED);
```

* `MONITOR` command:
	+ `LED` is the monitored device.
	+ `2` is the monitored channel.
	+ `0` is the monitored state.
	+ `0` is the monitored condition.
	+ `1.5` is the monitored time.
	+ `‘passed’` is the monitored message.
* `MOVE` command:
	+ `ARM` is the device to be moved.
	+ `fgoal` is the goal position.
	+ `LED` is the device to be monitored.

This example sets up a monitor for the LED device on channel 2. When the LED device is in state 0 for 1.5 seconds, it will display the message "passed". If the monitored condition is met, the ARM device will move to the fgoal position.

2. **Example 2:**

```
ATTN: SUBR;
MOTPARMS: NEW STOPMOVE;
WAITMOVE;
BREAK (EOL, ‘ATTENTION REQUESTED’);
APPLY (‘AMOVE’, MOTPARMS);
END;
```

* `ATTN` command:
	+ `SUBR` is the attention subroutine.
* `MOTPARMS` command:
	+ `NEW STOPMOVE` is the motion parameter.
* `WAITMOVE` command:
	+ Waits for the motion to complete.
* `BREAK` command:
	+ `EOL` is the break condition.
	+ `‘ATTENTION REQUESTED’` is the break message.
* `APPLY` command:
	+ `‘AMOVE’` is the command to apply.
	+ `MOTPARMS` is the parameter to apply.
* `END` command:
	+ Ends the attention subroutine.

This example defines an attention subroutine that sets the motion parameters to NEW STOPMOVE, waits for the motion to complete, breaks if the condition EOL is met, and applies the AMOVE command with the MOTPARMS parameter.

3. **Example 3:**

```
DMOVE (<4,5,6>,<30,-60,90>);
```

* `DMOVE` command:
	+ `<4,5,6>` is the device to be moved.
	+ `<30,-60,90>` is the goal position.

This example moves device 4 to position 30, device 5 to position -60, and device 6 to position 90.

4. **Example 4:**

```
SPEED (0.8)
```

* `SPEED` command:
	+ `0.8` is the speed setting.

This example sets the speed to 0.8.


-------------

Explain the following code & output when executed in AML:
i. MONITOR (LED, 2,0,0,1.5, ‘passed’);
MOVE (ARM, fgoal, LED);
ii. ATTN: SUBR;
MOTPARMS: NEW STOPMOVE;
WAITMOVE;
BREAK (EOL, ‘ATTENTION REQUESTED’);
APPLY (‘AMOVE’, MOTPARMS);
END;
iii. DMOVE (<4,5,6>,<30,-60,90>);
iv. SPEED (0.8);
v. IF SENSIO (LED, 0) THEN
BREAK (‘Part gripped’);
vi. TRAP: SUBR(NUM, DATA);
DISPLAY (‘ERROR NUMBER=’, NUM, EOL);
IF? DATA THEN
DISPLAY (‘ERROR DATA=’, DATA, EOL);
BRANCH(RETRY);
END;
ERRTRAP(‘TRAP’);


Let's break down each code snippet and explain what it does:

**i. MONITOR (LED, 2,0,0,1.5, ‘passed’);**
**MOVE (ARM, fgoal, LED);**

* The `MONITOR` command is used to monitor a digital input (in this case, an LED) and wait for a specific condition to be met. The parameters are:
	+ `LED`: the digital input to monitor
	+ `2`: the expected value of the input (likely a binary value, 0 or 1)
	+ `0`: the timeout value (in seconds)
	+ `0`: the debounce time (in seconds)
	+ `1.5`: the monitoring period (in seconds)
	+ `‘passed’`: the message to display when the condition is met
* The `MOVE` command is used to move the arm to a goal position (`fgoal`) while monitoring the LED input. If the LED input meets the condition specified in the `MONITOR` command, the arm will move to the goal position.

Output: The arm will move to the goal position (`fgoal`) when the LED input meets the condition specified in the `MONITOR` command.

**ii. ATTN: SUBR;**
**MOTPARMS: NEW STOPMOVE;**
**WAITMOVE;**
**BREAK (EOL, ‘ATTENTION REQUESTED’);**
**APPLY (‘AMOVE’, MOTPARMS);**
**END;**

* The `ATTN` label defines a subroutine that will be called when an attention request is made.
* The `MOTPARMS` command is used to set motion parameters. In this case, it sets the motion type to `STOPMOVE`, which means the robot will stop moving when the attention request is made.
* The `WAITMOVE` command waits for the robot to complete its current move before executing the next command.
* The `BREAK` command is used to interrupt the current program flow and display a message (`‘ATTENTION REQUESTED’`) when the attention request is made.
* The `APPLY` command applies the motion parameters set by `MOTPARMS` to the `AMOVE` motion type.
* The `END` statement marks the end of the subroutine.

Output: When an attention request is made, the robot will stop moving, and the message `‘ATTENTION REQUESTED’` will be displayed.

**iii. DMOVE (<4,5,6>,<30,-60,90>);**

* The `DMOVE` command is used to move the robot to a destination position specified by a set of coordinates.
* The first set of coordinates (`<4,5,6>`) specifies the linear movement (x, y, z axes).
* The second set of coordinates (`<30,-60,90>`) specifies the angular movement (roll, pitch, yaw axes).

Output: The robot will move to the specified position and orientation.

**iv. SPEED (0.8);**

* The `SPEED` command sets the robot's speed to 0.8 ( likely a value between 0 and 1, where 1 is the maximum speed).

Output: The robot's speed will be set to 0.8.

**v. IF SENSIO (LED, 0) THEN**
**BREAK (‘Part gripped’);**

* The `SENSIO` command is used to read the state of a digital input (in this case, an LED).
* The `IF` statement checks the state of the LED input. If it is 0, the program will execute the `BREAK` command.
* The `BREAK` command is used to interrupt the current program flow and display a message (`‘Part gripped’`).

Output: If the LED input is 0, the program will display the message `‘Part gripped’` and interrupt the current program flow.

**vi. TRAP: SUBR(NUM, DATA);**
**DISPLAY (‘ERROR NUMBER=’, NUM, EOL);**
**IF? DATA THEN**
**DISPLAY (‘ERROR DATA=’, DATA, EOL);**
**BRANCH(RETRY);**
**END;**
**ERRTRAP(‘TRAP’);**

* The `TRAP` label defines a subroutine that will be called when an error occurs.
* The `SUBR` command defines a subroutine that takes two parameters: `NUM` and `DATA`.
* The `DISPLAY` command is used to display error messages. The first message displays the error number (`NUM`), and the second message displays the error data (`DATA`) if it is not null.
* The `BRANCH` command is used to jump to a label (`RETRY`) when an error occurs.
* The `ERRTRAP` command sets the error trap subroutine to `TRAP`.

Output: When an error occurs, the program will display the error number and data (if available) and jump to the `RETRY` label.

