Singularities in robotics refer to specific configurations or positions of a robotic manipulator arm where it loses one or more degrees of freedom (DOF) and experiences a loss of control or maneuverability. At these singular configurations, the robotic arm becomes unstable, and its motion becomes unpredictable or undefined.

Detecting collisions between robots or between a robot and its surroundings is crucial for ensuring safe and efficient operation in industrial and collaborative settings. Here are some common methods used for collision detection and features added to avoid collisions:

1. Workspace Monitoring:
   - Sensor-based collision detection: This method uses various sensors, such as laser scanners, vision systems, or proximity sensors, to continuously monitor the robot's workspace and detect any obstacles or other robots in its vicinity.
   - Virtual/software-based collision detection: The robot's workspace and the positions of other robots or obstacles are represented virtually in software. The system checks for intersections or violations of defined safety zones to detect potential collisions.

2. Path Planning and Trajectory Generation:
   - Collision avoidance path planning: The robot's motion paths and trajectories are planned in advance, considering the positions and movements of other robots or obstacles. Algorithms, such as potential field methods or rapidly-exploring random trees (RRT), are used to generate collision-free paths.
   - Real-time trajectory modification: If an obstacle or another robot is detected during operation, the robot's trajectory can be dynamically modified or replanned to avoid collisions.

3. Force/Torque Sensing:
   - Collision detection through force/torque sensors: Robots equipped with force/torque sensors in their joints or end-effectors can detect unexpected forces or torques caused by collisions. This information can be used to trigger emergency stops or reactive behaviors.

4. Sensor Fusion and Redundant Sensing:
   - Combining multiple sensor modalities: By fusing data from different types of sensors (e.g., vision, laser, proximity), the system can achieve more robust and reliable collision detection.
   - Redundant sensing: Using multiple sensors of the same type at different locations or orientations can provide redundancy and improve reliability in detecting collisions.

5. Safety-Rated Components and Systems:
   - Safety-rated controllers and software: Industrial robots often use safety-rated controllers and software designed to meet specific safety standards and regulations, ensuring proper handling of collision detection and avoidance scenarios.
   - Safety-rated sensors and devices: Sensors and devices used for collision detection are designed and certified to meet safety requirements, ensuring reliable and consistent performance.

6. Collaborative Robot Features:
   - Soft and compliant materials: Collaborative robots (cobots) often incorporate soft and compliant materials in their exterior surfaces or joints, reducing the potential for injury in case of unintended collisions with humans.
   - Inherent force/torque limitations: Cobots are designed with inherent force and torque limitations, allowing them to operate safely in close proximity to humans and minimizing the risk of injury in case of collisions.

7. Operational Modes and Safeguarding:
   - Safety-rated operational modes: Robots can operate in different modes (e.g., reduced speed, restricted workspace) depending on the presence of humans or other robots in the vicinity, reducing the risk of collisions.
   - Physical safeguarding: In addition to collision detection systems, physical barriers, fences, or light curtains can be used to separate the robot's workspace from human-accessible areas, preventing unintended collisions.

The specific methods and features employed for collision detection and avoidance depend on the application, the robot's capabilities, and the safety requirements of the industrial or collaborative setting. Combining multiple approaches and incorporating redundant systems is often recommended for maximizing safety and reliability.