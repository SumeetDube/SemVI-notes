In Numerical Control (NC) and Computer Numerical Control (CNC) systems, the programming language consists of various "words," which are codes that define specific commands or functions. These words are composed of a letter followed by a numerical value. Here are some key word functions:

1. **N Word (Sequence Number)**
    
    - Specifies the order of operations in the program.
    - Example: N0010 G01 X100 Y100 F150
2. **G Word (Preparatory Functions)**
    
    - Defines the type of operation or motion.
    - Example: G01 (linear interpolation), G02 (circular interpolation clockwise)
3. **X, Y, Z Words (Coordinate Words)**
    
    - Define the end point coordinates for the tool movement.
    - Example: X100 Y50 Z25
4. **I, J, K Words (Arc Center Coordinates)**
    
    - Specify the center point of an arc in circular interpolation.
    - Example: G02 X50 Y50 I25 J25
5. **F Word (Feed Rate)**
    
    - Specifies the speed at which the tool moves through the material.
    - Example: F200 (feed rate of 200 units per minute)
6. **S Word (Spindle Speed)**
    
    - Sets the spindle speed in revolutions per minute (RPM).
    - Example: S1500
7. **T Word (Tool Selection)**
    
    - Indicates the tool number to be used for the operation.
    - Example: T03 (selects tool number 3)
8. **M Word (Miscellaneous Functions)**
    
    - Controls auxiliary functions such as spindle on/off, coolant on/off, program stop.
    - Example: M03 (spindle on clockwise), M08 (coolant on)
9. **H Word (Tool Length Offset)**
    
    - Specifies the tool length offset number.
    - Example: G43 H01 Z10.0
10. **D Word (Cutter Diameter Compensation)**
    
    - Specifies the cutter diameter offset number.
    - Example: G41 D01

### Advantages of DNC Over NC/CNC

Distributed Numerical Control (DNC) systems offer several advantages over traditional NC and CNC systems. Here is a comparison in table format:

| **Aspect**                    | **NC/CNC**                                                  | **DNC**                                             |
| ----------------------------- | ----------------------------------------------------------- | --------------------------------------------------- |
| **Program Storage**           | Stored locally on the machine controller.                   | Stored on a central server or network.              |
| **Program Transfer**          | Manual transfer using physical media (tapes, disks).        | Automatic transfer via network.                     |
| **Program Management**        | Individual management of each machine's programs.           | Centralized management of all programs.             |
| **Updates and Modifications** | Manual updates required for each machine.                   | Easy and quick updates from the central server.     |
| **Data Backup**               | Limited to local backups.                                   | Centralized backup, easier to manage.               |
| **Error Reduction**           | Higher risk of errors dguring manual transfer.              | Reduced errors due to automated transfers.          |
| **Maintenance**               | Requires individual maintenance of each machine's software. | Centralized maintenance and easier updates.         |
| **Scalability**               | Adding new machines requires individual setup.              | New machines can be added easily to the network.    |
| **Real-Time Monitoring**      | Limited to local machine monitoring.                        | Centralized, real-time monitoring and control.      |
| **Collaboration**             | Difficult to share programs between machines.               | Easy sharing and standardization of programs.       |
| **Production Efficiency**     | Limited to the capabilities of individual machines.         | Optimized production flow with centralized control. |
|                               |                                                             |                                                     |
