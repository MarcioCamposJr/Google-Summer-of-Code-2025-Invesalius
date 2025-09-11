## Week 4

In the fourth week, the main focus was on improving robot identification and control, allowing users to define the active robot more flexibly and ensuring proper message handling for multi-robot setups. The key activities included:

- Robot ID via Argument
    - Enabled users to define the desired robot_ID through command-line arguments (argv) in the main loop.
    - Added robot_ID as an additional initialization variable for main_loop.

- Active Robot Switching Based on Coil Selection
    - Implemented logic to change the active robot according to the coil attached to it and the main coil selected in the navigation screen.
    - Developed helper functions within Robots to set a robot as active based on the coil association.
    - Displayed the name of the active robot above its related functions in the navigation screen (with possible future adjustments).

- Remote Control Differentiation (InVesalius Integration)
    - Introduced a new variable, robot_ID, in the messages exchanged with the robot to correctly identify the active robot.
    - Ensured proper differentiation of robots when sending commands and receiving data.
    - Updated functions triggered by robot messages to include the robot_ID parameter (e.g., Robot to Neuronavigation communications).
    - Extended message handling to send robot_ID with all robot-related messages listed under “Messages associated with the robot.”