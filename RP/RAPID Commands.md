i. AccSet
ii. SetDO
iii. MoveAbsJ
iv. ISignalDO
v. WaitDO
vi. MoveL
vii. ClearPath
viii. GripLoad
ix. TriggL
x. StopMove
xi. CONNECT
xii. IDelete

i) AccSet
ii) SetDO
iii) MoveAbsJ
iv) ISignalDO
v) WaitDO
vi) MoveL

1. **AccSet (Acceleration Set)**: Sets the acceleration for the next movement.

Example program:
```
PROC myProgram
  AccSet v:=100, a:=50;
  ! Set acceleration to 50 mm/s^2 for the next movement
  MoveL reltool:=TRUE, v:=100, a:=50, x:=300, y:=200, z:=100;
ENDPROC
```
In this example, the program sets the acceleration to 50 mm/s^2 for the next movement, which is the `MoveL` instruction.

2. **SetDO (Set Digital Output)**: Sets the state of a digital output.

Example program:
```
PROC myProgram
  SetDO DO1:=TRUE;
  ! Set digital output 1 high
  Wait 1; ! Wait for 1 second
  SetDO DO1:=FALSE;
  ! Set digital output 1 low
ENDPROC
```
In this example, the program sets digital output 1 high, waits for 1 second, and then sets it low.

3. **MoveAbsJ (Absolute Joint Move)**: Moves the robot to an absolute joint position.

Example program:
```
PROC myProgram
  MoveAbsJ reltool:=TRUE, v:=50, a:=20, j1:=30, j2:=45, j3:=60;
  ! Move to joint position (30, 45, 60) with a velocity of 50 deg/s and acceleration of 20 deg/s^2
ENDPROC
```
In this example, the robot moves to the joint position (30, 45, 60) with a velocity of 50 deg/s and acceleration of 20 deg/s^2.

4. **ISignalDO (Input Signal Digital Output)**: Sets the state of a digital output based on the state of a digital input.

Example program:
```
PROC myProgram
  ISignalDO DI1:=DO1;
  ! If digital input 1 is high, set digital output 1 high, otherwise set it low
ENDPROC
```
In this example, the program sets digital output 1 high if digital input 1 is high, and low if digital input 1 is low.

5. **WaitDO (Wait for Digital Output)**: Waits for a digital output to change state.

Example program:
```
PROC myProgram
  WaitDO DO1:=FALSE;
  ! Wait for digital output 1 to become low
ENDPROC
```
In this example, the program waits for digital output 1 to become low.

6. **MoveL (Linear Move)**: Moves the robot to a target position in a straight line.

Example program:
```
PROC myProgram
  MoveL reltool:=TRUE, v:=100, a:=50, x:=300, y:=200, z:=100;
  ! Move to position (300, 200, 100) with a velocity of 100 mm/s and acceleration of 50 mm/s^2
ENDPROC
```
In this example, the robot moves to the position (300, 200, 100) with a velocity of 100 mm/s and acceleration of 50 mm/s^2.

7. **ClearPath (Clear Path)**: Clears the robot's path.

Example program:
```
PROC myProgram
  ClearPath;
  ! Clear the robot's path
ENDPROC
```
In this example, the program clears the robot's path.

8. **GripLoad (Grip Load)**: Sets the grip load for the next movement.

Example program:
```
PROC myProgram
  GripLoad 50;
  ! Set the grip load to 50
  MoveL reltool:=TRUE, v:=100, a:=50, x:=300, y:=200, z:=100;
ENDPROC
```
In this example, the program sets the grip load to 50 for the next movement, which is the `MoveL` instruction.

9. **TriggL (Trigger Linear Move)**: Triggers a linear move.

Example program:
```
PROC myProgram
  TriggL;
  ! Trigger a linear move
ENDPROC
```
In this example, the program triggers a linear move.

10. **StopMove (Stop Movement)**: Stops the robot's movement.

Example program:
```
PROC myProgram
  StopMove;
  ! Stop the robot's movement
ENDPROC
```
In this example, the program stops the robot's movement.

11. **CONNECT (Connect)**: Connects to a robot.

Example program:
```
PROC myProgram
  CONNECT;
  ! Connect to a robot
ENDPROC
```
In this example, the program connects to a robot.

12. **IDelete (Instruction Delete)**: Deletes an instruction.

Example program:
```
PROC myProgram
  IDelete 1;
  ! Delete instruction 1
ENDPROC
```
In this example, the program deletes instruction 1.