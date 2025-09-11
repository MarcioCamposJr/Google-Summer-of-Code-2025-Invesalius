## Week 7

During the seventh week, the focus was on improving usability in multi-coil navigation, refining coil–robot–marker associations, and ensuring safer transitions when changing the main coil. The main activities included:

- Coil/Robot and Marker Selection Control
    - Enhanced usability of the multi-coil workflow.
    - Updated selection box to display both coil and its associated robot.
    - Added coil indicator in the markers table for clearer identification.
    - Implemented checks to ensure a robot is properly associated with a coil, preventing errors.
    - Added robot name display in coil selection.
    - Added a new column in the markers table for coil information.
    - Prevented navigation with markers linked to outdated/nonexistent coils:
        - Instead of deleting them, the system shows a warning message.
    - Allowed explicit association between markers and coils.
    - Implemented reset of all coil registrations whenever the number of coils is changed.
    - Cleared all targets when the number of coils is redefined.
    - Added coil assignment when creating a target from a landmarker.
    - Removed coils from fiducial markers to avoid conflicts.
    - Blocked coil switching while navigating with an active target.
    - Added a button to change the coil associated with a marker.

- Main Coil Switching Improvements
    - Implemented logic to stop ongoing robot actions before switching the main coil.
    - Improved the process of replacing one coil with another as the main coil to avoid unsafe or conflicting actions.
    - Published a "Press robot button" message through SetActiveByCoil to ensure confirmation during coil switching.