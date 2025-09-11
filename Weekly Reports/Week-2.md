## Week 2

In the second week, the work focused on replacing the use of coil IDs with coil names, improving usability during registration and navigation, and ensuring consistency across the interface and backend. The main activities included:

- Transition from ID to Coil Name
    - Replaced coil ID with coil name as the primary reference for registration and navigation.
    - Removed the ID field from registration options and replaced it with the pre-defined coil name.
    - Updated tooltips and interface elements to reflect this change.
    - Implemented automatic retrieval of coil names from the marker file.
    - Allowed coil name changes directly from the selection box.
    - Added a warning screen to prevent duplicate names.

- Registration and Data Consistency
    - Ensured correct saving of coordinates for the corresponding coils.
    - Implemented conflict handling between save and load operations to avoid data overwrite.
    - Preserved coil name consistency when modified in pre-configurations.

- User Experience Adjustments
    - Removed the dedicated text box for editing coil names, centralizing renaming within the selection interface.
    - Improved error handling and feedback for users when naming conflicts occurred.