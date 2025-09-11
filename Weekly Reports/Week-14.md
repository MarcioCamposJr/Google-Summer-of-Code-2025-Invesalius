## Week 14

In the fourteenth week, the focus was on fixing issues related to coil–target associations and marker behavior across navigation windows. The main activities included:

- Error in Coil-to-Coil Association
    - Fixed an error that occurred when attempting to change the coil associated with another coil.

- Orientation Coil Added to Wrong Target Window
    - Identified an issue where the first target set for coil_1 also added an orientation coil in the second window.
    - Corrected the behavior to ensure orientation coils appear only in the intended window.

- Switching Coils Associated with Coil Targets
    - Fixed errors occurring when changing the coil associated with a marker’s coil target in the markers panel.
    - Ensured proper reassignment of coil targets without disrupting navigation or marker data.