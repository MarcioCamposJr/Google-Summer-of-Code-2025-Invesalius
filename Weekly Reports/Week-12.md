## Week 12

In the twelfth week, the focus was on enhancing error handling, supporting multi-robot multi-target navigation, and saving project-specific settings for multitarget mode. The main activities included:

- Error Reset Functionality
    - Implemented a global function to reset errors during experiments.
    - Added corresponding pub-sub messages for real-time updates.
    - Extended support for multiple robot types:
        - Dobot CR
        - HansRobot Elfin
        - Universal Robots

- Multi-Robot Navigation with Two Targets
    - Enabled navigation of two robots simultaneously towards separate targets.
    - Updated robot control messaging to send commands separately for each robot.
    - Checked for internal control conflicts to ensure safe multi-robot operation.
    - Managed individual target reach notifications for each robot.

- Project-Specific Multitarget Mode
    - Implemented saving of the multitarget mode within the project.
    - Ensured that changing the project automatically disables multitarget mode if not configured.