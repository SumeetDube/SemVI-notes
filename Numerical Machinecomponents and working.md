
A Numerical Control (NC) system is used in manufacturing processes to control machine tools through the use of programmed commands encoded on a storage medium. The basic components of an NC system are essential for its operation and can be broadly categorized into the following:


```
Input -> MCU -> Drive System - > Machine -Tool -> feedback system ->
```
![[Pasted image 20240520213459.png]]
![[Pasted image 20240520213517.png]]
1. **Input Device:**
    
    - **Function:** The input device is used to input the part program (set of instructions) into the NC system. This can be done through punched tapes, magnetic tapes, or more modern methods like computer-aided design (CAD) files or direct numerical control (DNC) systems.
    - **Examples:** Punched cards, magnetic tapes, USB drives, computer interfaces.
2. **Machine Control Unit (MCU):**
    
    - **Function:** The MCU is the brain of the NC system. It reads the input program and translates the instructions into electrical signals that control the machine tool. It consists of several sub-components, including:
        - **Data Processing Unit (DPU):** Interprets the part program and processes the data.
        - **Control Processing Unit (CPU):** Generates the control signals for the machine tools.
    - **Examples:** Microcontrollers, industrial computers, specialized NC controllers.
3. **Machine Tool:**
    
    - **Function:** The machine tool is the actual device that performs the manufacturing operation. The MCU controls its movement and operation based on the instructions received from the part program. It can perform various operations like milling, turning, drilling, etc.
    - **Examples:** CNC milling machines, CNC lathes, CNC drilling machines.
4. **Drive System:**
    
    - **Function:** The drive system includes motors and other mechanical components that move the machine tool along its axes. The drive system receives signals from the MCU to control the position and speed of the tool.
    - **Examples:** Servo motors, stepper motors, linear actuators.
5. **Feedback System:**
    
    - **Function:** The feedback system ensures the precision and accuracy of the machine tool's movements. It monitors the actual position and speed of the machine tool and sends this information back to the MCU to correct any discrepancies from the desired values.
    - **Examples:** Encoders, resolvers, linear scales.
6. **Display Unit:**
    
    - **Function:** The display unit provides a visual interface for the operator to interact with the NC system. It displays information about the current status of the machine, the part program, error messages, and other relevant data.
    - **Examples:** Monitors, touch screens, indicator panels.
7. **Control Panel:**
    
    - **Function:** The control panel allows the operator to manually input commands, start and stop the machine, and override the automatic operations if necessary. It typically includes buttons, switches, and dials for various controls.
    - **Examples:** Keypads, joysticks, manual input devices.

### Summary of Functions:

- **Input Device:** Input part programs into the system.
- **Machine Control Unit (MCU):** Process and execute the part program instructions.
- **Machine Tool:** Perform the manufacturing operations.
- **Drive System:** Control the movements of the machine tool.
- **Feedback System:** Ensure accuracy and precision of operations.
- **Display Unit:** Provide visual interface and information to the operator.
- **Control Panel:** Enable manual control and interaction with the system.




------------------
NC (Numerical Control) machines are automated systems that rely on computer programming and precise numerical data to control their movements and operations. By eliminating the need for manual intervention and enhancing precision, NC machines have drastically improved production efficiency, accuracy, and repeatability in various industries. The advent of NC machines has given rise to CNC (Computer Numerical Control) machines, which further integrate computers to control their functionalities, enabling even more sophisticated and intricate machining processes.

## What is an NC Machine?

NC (Numerical Control) machine is a type of automated manufacturing system that utilises computer programming and a predefined set of alphanumeric codes to control the movements and operations of specific tools. These codes carry essential information for guiding the tool's movements. Unlike traditional machines, where manual labourers manually control various parameters such as motor speed, feed rate, rotation direction, and depth of cut. NC machines utilise a control panel to govern all these parameters efficiently and precisely. By employing these alphanumeric codes, NC machines have streamlined the manufacturing process, offering enhanced [accuracy](https://testbook.com/maths/accuracy) and automation for various machining operations.

## Types of NC Systems

There are three types of NC machines:

### Traditional Numerical Control (NC Machine)

NC machines are an evolution of conventional machines and can operate using a tape reader system. Instructions for desired operations are punched onto a tape, enabling the NC machine to perform the specified tasks.

### Computer Numerical Control (CNC Machine)

CNC machines emerged after NC machines to overcome their limitations. Instead of using a tape reader, CNC machines utilise a computer-generated file containing G-Codes and M-Codes to store the program. This allows for instant changes to parameters like speed, feed, and depth of cut, making CNC machines highly accurate and efficient.

### Distributed Numerical Control (DNC Machine)

Similar to CNC machines, DNC machines employ a remote computer to control multiple machines performing various operations simultaneously. The central or remote computer communicates with local CNC computers to execute the operations.

## Basic Components of NC machine

![](https://blogmedia.testbook.com/blog/wp-content/uploads/2023/08/nc-machines-9ccff68c.png)

Fig: NC machine diagram

The fundamental components of an NC (Numerical Control) machine are as follows:

	- Set of instructions 
	- Machine Control Unit(MCU)
	- Signal Output Channel
	- Tape Reader
	- Data Buffer
	- Feedback Channel and
	- Machine Tools.

Set of Instructions: A complete set of step-by-step instructions that dictate the actions of the machine tool, coded in a numeric or symbolic form for interpretation by the controller unit. Input media for NC machines have evolved over time, with L-in-wide tapes being the most common today. Other methods include manual data input (MDI) for simple tasks and direct numerical control (DNC) linked with computers.

Machine Controller Unit: Comprising electronics and hardware, this unit reads and interprets the program of instructions, converting them into mechanical functions of the machine tool. It controls equipment passages, feeds, tool changes, and other operations. Components of a traditional NC controller unit include tape readers, data buffers, signal channels, feedback channels, and sequence coordinators.

Machine Tool: This component performs the intended functions within the NC system and can be any type of machine tool or equipment. In typical machining operations, machine tools are designed with a worktable, spindle-like motor, and controls necessary for their operation. The machine tool includes cutting tools, work fixtures, and auxiliary equipment essential for the machining process.

Drive Units (Servo Motors): The machine's axes are driven by powerful DC servomotors mounted on preloaded ball [bearings](https://testbook.com/mechanical-engineering/bearings). Signals from the control unit activate the servomotors, causing the machine slides to move to achieve the desired length of travel and feed rate. The drive units may use hydraulic DC motors or stepping motors.

Feedback Unit: Also known as the position feedback package, this unit provides information about the actual position of movements to the control unit. The control unit compares the actual movements with the required ones and makes necessary corrections by actuating the drive units.

Magnetic Box: Responsible for receiving electric signals from the control unit for various machine activities, excluding servo motor drives. The magnetic box controls spindle motor start/stop, spindle speed selection, tool changes, coolant supply, and other functions.

Control Panel (Manual Control): The control panel, either part of the controller unit or machine tool, allows the machine operator to interact with the NC system using dials and switches for running the machine.

## Classification of NC machines

NC machines can be classified based on the following conditions:

- According to motion control
- According to control loops
- Based on power supply
- According to positioning system

### According to Motion Control

- **Point to Point Mechanism:** The workpiece or spindle moves from one specified position to another for performing operations like numeric control drilling. It is the simplest and most cost-effective method.
- **Straight Cut Mechanism:** The cutting tool moves parallel to one of the axes (X, Y, or Z) at a controlled rate, is suitable for milling rectangular workpieces, and can also perform point-to-point movements.
- **Contouring Mechanism:** This complex and expensive mechanism controls two or more axes simultaneously to achieve desired shapes. The workpiece moves along a continuous path, allowing the tool to work while axes are in motion, producing angular surfaces and 2D or 3D curves.

### According to Control Loops

- **Open Loop:** Instructions are given to the [motor](https://testbook.com/physics/types-of-motors) by the controller without precise movement and direction, but it can still achieve the desired shape. It is a more affordable option.
- **Closed Loop:** Utilises sensors, [transducers](https://testbook.com/physics/transducer), and counters to accurately estimate the table's position. It uses a feedback unit to compare the workpiece position with signals from the controller unit, making it a more expensive and intricate system.

### Based on Power Supply

- **Electric:** Utilises AC and DC motors with complicated wiring and control systems using circuits.
- **Hydraulic:** Utilises [hydraulic pumps](https://testbook.com/physics/hydraulic-machines) and rams to provide power, offering high torque and rapid response, suitable for specific operations.
- **Pneumatic System:** Rarely used in NC machining due to its large size and low [torque](https://testbook.com/physics/torque).

### According to Positioning System

- **Incremental Positioning:** The change in the previous position serves as the reference point for determining the next position.
- **Absolute Positioning:** The point of origin is taken as the reference point, requiring the control unit to calculate the position independently.

Also, learn about [IC Engine](https://testbook.com/mechanical-engineering/ic-engine-full-form-diagram-and-classification).

## NC Machine Working Principle

The steps to employ the NC machine in the manufacturing process are as follows:

### Planning Process

This stage involves interpreting engineering drawings of the workpiece and determining the manufacturing processes required. A route sheet is prepared, outlining the series of operations that the workpiece must undergo.

### Programming Process

In this step, the programmer writes the program to sequence the operations or machining processes required for the workpiece. The programmed instructions are converted into output signals that control actions like spindle speed, tool selection, tool movement, and cutting fluid flow.

### Tape Preparation

The program is punched into a tape in this phase. For manual part programming, a typewriter-type device with tape-punching capability is used.

### Tape Inspection

After preparing the tape, it undergoes inspection to check for accuracy. Inspection methods can include using a computer program to simulate tool actions on paper or performing an "acid test," where the tool executes actions on a sample workpiece made of plastic or foam.

### Production

This final step involves using the NC tape for production. It includes managing the raw workpiece, specifying and preparing the required tooling and special fixtures, and setting up the NC machine for the operation.

Also, delve into the various aspects of the [Flywheel](https://testbook.com/mechanical-engineering/flywheel-definition-diagram-and-applications).

NC machines find extensive utilisation in the metal-cutting industry and excel in producing the following types of products:

- Parts with intricate contours.
- Parts requiring close tolerances and excellent repeatability.
- Parts that would necessitate expensive jigs and fixtures if produced on conventional machines.
- Parts undergoing frequent engineering changes, especially during prototype development.
- Situations where human errors could lead to significant costs.
- Urgently required parts.
- Small batch lots or short production runs.

## Advantages of NC Machine

The various advantages of NC Machines include:

- **Reduced Non-Productive Time:** NC machines increase productive working time by minimising non-productive movements such as tool changes and workpiece handling, reducing overall downtime.
- **Faster Completion of Work:** Automation of manual tasks like cutting and drilling speeds up the completion of work.
- **Greater Flexibility:** NC machines offer ease in design changes, adjusting production schedules, and accommodating rush orders.
- **Improved Quality:** NC machines excel at producing complex parts with high accuracy, leading to fewer human mistakes, reduced scrap, and lower inspection requirements.
- **Space Efficiency:** NC machines require less floor space compared to conventional machines due to their automated tooling system.
- **User-Friendly Operation:** NC machines are easily operated by less skilled labour, as the processes are automated, requiring minimal manual intervention.
- **Elimination of Human Errors:** Automation minimises human errors, ensuring consistent and reliable results.
- **Labour Cost Reduction:** The implementation of NC technology reduces labour costs as it requires minimal human involvement compared to conventional machines.
- **High Dimensional Accuracy:** NC machines deliver superior dimensional accuracy compared to conventional machines, ensuring precision in the manufacturing process.

## Disadvantages of NC Machine

NC machines suffer from some disadvantages as well:

- **High Investment Required:** Implementing NC machines demand a substantial initial investment due to their intricate and complex technology. The management must use the machines aggressively to recover costs through higher production and achieve a satisfactory return on investment.
- **Higher Maintenance Cost:** NC machines experience considerable wear and tear due to their heavy usage, necessitating more frequent and costly maintenance compared to conventional machines.
- **Involves Trained NC Personnel:** Operating NC machines requires highly trained personnel with expertise in handling intricate technology, making it challenging to find, hire, and train skilled employees, leading to higher costs and time investment.
- **Programming Training Required:** Making changes to the NC machine and troubleshooting issues demand individuals with in-depth knowledge of NC programming, further emphasising the need for specialised training and expertise.

