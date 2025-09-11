## Week 1

During the first week, the focus was on improving the coil selection interface, enhancing connection handling with the tracker, and refining the coil registration process. The main activities were:

- Coil Selection Interface

    - Redesigned the interface to be more descriptive and user-friendly.
    - Added a button to rename coils and included validation to avoid duplicate names.
    - Corrected the logic for coil selection and deselection, ensuring proper interaction.
    - Limited coil selection to situations where the tracker is connected.
    - Fixed title index updates within the coil selection frame.
    - Implemented pub-sub functions to reset saved coils in the configuration and remove associated buttons.
    - Added a “no_coil” message to handle empty selection cases.
    - Reviewed coil registration rules to correctly display updated names after renaming.

- Tracker Connection Pre-set
    - Added functionality to save the last tracker connection (IP address).
    - Stored the most recent IP in the configuration and automatically set it in the selection box for future connections.

- Coil Registration Auto-reset
    - Simplified the process by removing an unnecessary reset command.
    - Prevented coordinate reset when the coil ID is changed, ensuring that prior records are preserved.