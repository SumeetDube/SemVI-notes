**Definition of Motion Command:**

A Motion Command is a instruction in AML (A Manufacturing Language) that controls the movement of a robot or a machine. It specifies the type of motion, the destination, and other parameters such as speed, acceleration, and tool selection. Motion Commands are used to program the robot's movements to perform tasks such as welding, painting, assembly, and material handling.

**7 Move Motion Commands used in AML:**

1. **Linear Move Motion Command:**

    * Syntax: `MOVL P[position_number]`
    * Example: `MOVL P[100]`
    * Explanation: The `MOVL` command is used to move the robot linearly to a specified position. In this example, the robot will move linearly to position 100.

2. **Circular Move Motion Command:**

    * Syntax: `MOVC P[position_number], P[position_number], I[tool_number]`
    * Example: `MOVC P[100], P[200], I[1]`
    * Explanation: The `MOVC` command is used to move the robot in a circular path from one position to another. In this example, the robot will move in a circular path from position 100 to position 200 using tool 1.

3. **Rapid Move Motion Command:**

    * Syntax: `MOVR P[position_number]`
    * Example: `MOVR P[100]`
    * Explanation: The `MOVR` command is used to move the robot rapidly to a specified position. In this example, the robot will move rapidly to position 100.

4. **Synchronous Move Motion Command:**

    * Syntax: `MOVS P[position_number], P[position_number], ...`
    * Example: `MOVS P[100], P[200], P[300]`
    * Explanation: The `MOVS` command is used to move multiple axes synchronously to specified positions. In this example, axes 1, 2, and 3 will move simultaneously to positions 100, 200, and 300, respectively.

5. **Blending Move Motion Command:**

    * Syntax: `MOVB P[position_number], P[position_number], ...`
    * Example: `MOVB P[100], P[200], P[300]`
    * Explanation: The `MOVB` command is used to move multiple axes in a blended motion. In this example, axes 1, 2, and 3 will move in a blended motion to positions 100, 200, and 300, respectively.

6. **Continuous Move Motion Command:**

    * Syntax: `MOVX P[position_number], P[position_number], ...`
    * Example: `MOVX P[100], P[200], P[300]`
    * Explanation: The `MOVX` command is used to move multiple axes in a continuous motion. In this example, axes 1, 2, and 3 will move continuously to positions 100, 200, and 300, respectively.

7. **Orient Move Motion Command:**

    * Syntax: `MOVO P[position_number], R[orientation_number]`
    * Example: `MOVO P[100], R[45]`
    * Explanation: The `MOVO` command is used to move the robot to a specified position and orientation. In this example, the robot will move to position 100 and orient itself at 45 degrees.

These seven Move Motion Commands are commonly used in AML to control the robot's motion and perform various tasks. Each command has a specific purpose and syntax, and they are used in different situations.