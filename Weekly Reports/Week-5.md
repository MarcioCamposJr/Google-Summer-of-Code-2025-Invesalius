## Week 5

In the fifth week, the focus was on refining the remote control handling for multiple robots and improving the coil-to-robot association in the interface. The main activities were:

- Remote Control Differentiation – Robot Control
    - Added a new variable to incoming messages to ensure proper robot identification.
    - Updated on_message_receive so that the main_loop responds only to the specified robot_ID.
    - Modified send_message to inform InVesalius which robot has reacted to the command.

- Robot–Coil Selection
    - Enhanced the coil selection interface to improve clarity in defining coil–robot associations.
    - Introduced a new selection box for additional robots, allowing a coil to be assigned to each one.
    - Improved information flow to ensure each robot receives data only from its associated coil.