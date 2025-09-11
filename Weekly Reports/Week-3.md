## Week 3

During the third week, the focus was on restructuring the robot management architecture to support multiple robot instances, refining the configuration handling, and improving code maintainability. The main activities were:

- Refactoring Robot Creation (InVesalius Integration)
    - Removed the Singleton parent class previously tied to the Robot class in robot.py.
    - Created a new Robots class in robot.py, which manages two Robot objects and inherits from Singleton.
    - Introduced an ID system (robot_name) to track multiple robot instances.
    - Updated class assignments throughout the code, replacing Robot references with Robots.
    - Modified main function calls (e.g., from self.robot.SendTargetToRobot() to self.robot.GetActive().SendTargetToRobot()) to ensure functionality with the new structure.

- Second Robot Session Handling
    - Defined a method to create new robot connection sessions in preferences.py.
    - Refactored functions in preferences.py → TrackerTab for better clarity.
    - Extracted the Setup Robot logic into a dedicated SetupRobot class to improve code reuse and maintainability.
    - Implemented conditional creation of a second robot setup:
    - Created only when the number of coils selected is ≥ 2.
    - Destroyed when the number of coils returns to 1.

- Configuration Improvements for Multi-Robot Support
    - Restructured config.json to store information for multiple robots.
    - Changed key references from "robot" to "robots".
    - Moved "robot_ip_options" outside of "robots", since both share the same options.
    - Ensured that each robot stores its configuration separately under its own ID.
    - Added a new method SaveIpConfig to Robot.
    - Reassigned references in SaveConfig and LoadConfig methods to align with the new structure.
    - Split LoadConfig in TrackerTab into two parts, with one LoadConfig now inside SetupRobot.