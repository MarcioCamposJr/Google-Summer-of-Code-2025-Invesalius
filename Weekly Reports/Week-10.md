## Week 10

In the tenth week, the focus was on distributing navigation functions across multiple 3D windows, extending simultaneous navigation beyond two coils, and ensuring real-time updates of scene states. The main activities included:

- Function Distribution Across 3D Navigation Windows
    - Created a dedicated class to manage navigation windows and distribute core functions, including:
        - Updating the object arrow matrix.
        - Updating point locations for E-field calculations.
        - Retrieving the E-norm.
        - Setting targets.
        - Unsetting targets.
        - Updating coil poses.

- Simultaneous Navigation for More Than Two Coils
    - Added a selection box to define which coils will participate in navigation when more than two are present.
    - Extended the system logic to support simultaneous navigation beyond the previous two-coil limitation.

- Real-time Scene and Navigation State Updates
    - Implemented a threaded approach to update navigation windows dynamically during operation.
    - Added a loop to iterate over available coils and send pub-sub messages with coil names for proper distribution of updates across windows.