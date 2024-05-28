
.=G and M codes are essential components of CNC (Computer Numerical Control) programming, used to control and automate the operations of CNC machines. These codes are part of the programming language used to create instructions for CNC machines to perform specific tasks such as milling, turning, and drilling. Here is an overview of G and M codes:

### G Codes (Preparatory Functions)
G codes, also known as preparatory codes, define the mode or type of movement and coordinate system of the CNC machine. They prepare the machine for specific operations and control the geometry of the machining process. Common G codes include:

1. **G00** - Rapid Positioning:
   - Moves the tool to a specified location at the maximum speed of the machine. Used for non-cutting moves to reduce cycle time.

2. **G01** - Linear Interpolation:
   - Moves the tool in a straight line at a controlled feed rate, specified by the user. This code is used for precise cutting operations.

3. **G02** - Circular Interpolation Clockwise:
   - Commands the tool to move in a clockwise circular arc from the current position to a specified endpoint. The arc is defined by either the center point or the radius.

4. **G03** - Circular Interpolation Counter-Clockwise:
   - Similar to G02 but moves the tool in a counter-clockwise arc.

5. **G17/G18/G19** - Plane Selection:
   - G17: Selects the XY plane for circular interpolation.
   - G18: Selects the XZ plane.
   - G19: Selects the YZ plane.

6. **G20/G21** - Units Selection:
   - G20: Sets the machine to use inches for distance measurements.
   - G21: Sets the machine to use millimeters.

7. **G28** - Return to Home Position:
   - Moves the tool to the machine's predefined home position.

8. **G40/G41/G42** - Cutter Radius Compensation:
   - G40: Cancels cutter radius compensation.
   - G41: Compensates for the cutter radius to the left of the programmed path.
   - G42: Compensates for the cutter radius to the right of the programmed path.

9. **G90/G91** - Absolute/Incremental Positioning:
   - G90: Sets the machine to absolute positioning, where all coordinates are relative to a fixed origin.
   - G91: Sets the machine to incremental positioning, where each coordinate is relative to the current position.

### M Codes (Miscellaneous Functions)
M codes, or miscellaneous codes, control various machine functions that are not directly related to the movement or cutting path of the tool. These codes handle the auxiliary functions necessary for the machining process. Common M codes include:

1. **M00** - Program Stop:
   - Stops the machine's operation temporarily. The machine remains in this state until manually restarted.

2. **M01** - Optional Stop:
   - Similar to M00 but can be ignored if the optional stop function is not enabled on the machine's control panel.

3. **M02** - Program End:
   - Signals the end of the CNC program. The machine stops and resets.

4. **M03** - Spindle On (Clockwise):
   - Turns the spindle on and rotates it clockwise.

5. **M04** - Spindle On (Counter-Clockwise):
   - Turns the spindle on and rotates it counter-clockwise.

6. **M05** - Spindle Stop:
   - Stops the spindle from rotating.

7. **M06** - Tool Change:
   - Commands the machine to change the current tool to the specified tool number.

8. **M08** - Coolant On:
   - Turns the coolant system on to help manage heat during cutting operations.

9. **M09** - Coolant Off:
   - Turns the coolant system off.

10. **M30** - Program End and Rewind:
    - Ends the CNC program and rewinds it to the beginning, readying it for another cycle if needed.

Understanding and correctly using G and M codes is crucial for the effective programming and operation of CNC machines, enabling precise control over the machining processes and ensuring the desired outcomes in manufacturing.