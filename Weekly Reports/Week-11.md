## Week 11

During the eleventh week, the main focus was on improving multi-robot control during navigation, updating the interface layout, and addressing UI inconsistencies in multi-coil mode. The key activities included:

- Multi-Robot Control During Navigation
    - Managed the control flow for one or two robots, ensuring proper display and functionality of robot buttons.
    - Added a second set of buttons for the second robot.
    - Updated function bindings for each robot to guarantee independent operation.
    - Added visual indicators for referencing and status feedback.
    - Implemented button display logic to handle different scenarios (single or dual robot setups).
    - Added a new button to reset errors efficiently.

- Setup Robot UI Inversion in Multi-Coil Mode
    - bserved that the Setup Robot interface may invert depending on which coil is selected first in the preferences.
    - Noted potential bug: when InVesalius is opened in multi-coil mode, the Setup Robot UI can appear inverted.
    - Investigated the inversion issue to ensure consistent window layout across coils.