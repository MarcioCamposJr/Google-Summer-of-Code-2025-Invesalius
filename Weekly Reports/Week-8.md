## Week 8

In the eighth week, the efforts were directed toward simplifying navigation processes, improving coil visualization, and refining the behavior of the main coil in simultaneous navigation. The key activities included:

- Process Simplification – task_navigator
    - Reduced redundant processes for button creation, such as target_button_mode.
    - Streamlined task handling for improved maintainability.

- Visualization of Tracker-Detected Coils
    - Implemented a feature to show whether multiple coils are being detected by the tracker.
    - Added visual indicators in the scene:
        - Blue sphere → coil detected.
        - Red sphere → coil not detected.

- Main Coil Behavior Adjustment
    - Refined the role of the main coil so it is used only for marker creation, not for navigation.
    - Ensured that changing the main coil does not alter the VTK scene object linked to the navigation target.
    - Clarified that the main coil is associated with the robot, while navigation should remain tied to the active target (important for simultaneous navigation).
    - Removed the command that changed the robot when the main coil was altered.
    - Modified logic to:
        - Switch the robot only when a target is set.
        - Update the scene only when the target is set.
    - Added functionality to create coil targets based on the selected main coil.