## Week 9

During the ninth week, the focus was on enabling simultaneous navigation with multiple coils, supporting multitarget selection, and introducing a dual navigation window system. The main activities included:

- Simultaneous Multitarget Button
    - Added a dedicated button to activate simultaneous navigation mode with multiple coils.

- Multiple Target Selection for a Single Coil
    - Enabled the creation of multiple targets for a single coil when the simultaneous multitarget mode is active.
    - Enforced restrictions so multitargeting applies only within one coil at a time.

- Dual Navigation Window
    - Developed a dedicated class for managing navigation windows.
    - Implemented instantiation of two navigation windows, each associated with a different coil.
    - Added layout control for the windows:
        - Normal mode: 3 slices + 1 3D view.
        - Simultaneous mode: 2 separate 3D views.
    - Displayed coil names on the windows for clear identification.