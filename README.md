![Alt Text](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/cover.png)

# Google Summer of Code 2025 - Final Report
- Name : Marcio Adriano Campos Junior
- Organization : [InVesalius](https://invesalius.github.io/)
- Project : [Simultaneous visualization and control of Two Robots for Dual Transcranial Magnetic Stimulation](https://summerofcode.withgoogle.com/programs/2025/projects/vG6Rv7zY)
- Mentors : Renan Hiroshi Matsuda, Victor H. E. Malheiro, Lucas dos Santos Betioli, Thais Cunha Marchetti
- **(example)** Project Branch : [GSoC_2025_MarcioCamposJr]
- **(example)** Pull Request: [#945](https://github.com/invesalius/invesalius3/pull)(Merged) (Related issue - #923)

## Introduction
This project focuses on implementing simultaneous navigation capabilities for two Transcranial Magnetic Stimulation (TMS) coils within the InVesalius software. The core of the work was to adapt the system architecture to manage, visualize, and record two targets and two coils concurrently, overcoming the previous limitation of only one target at a time.

To enable the physical and precise positioning of these two coils, the project also included the development of a control structure for multiple robots. The implementation ranged from creating a dedicated navigation interface to managing multiple targets in the 3D scene. For robotic operation, a critical component was the development of safety algorithms to ensure that the coils would not collide.

## Project Goal
Integrate a functional system for dual-site Transcranial Magnetic Stimulation (TMS) procedures into the InVesalius software, enabling both manual and robotic navigation.

To achieve this primary objective, the following specific deliverables were defined:

- Enable simultaneous navigation and precise positioning of two TMS coils on distinct neural targets.

- Ensure independent control of each robot-coil assembly, when in use, through the software interface.

- Implement robust safety mechanisms to prevent collisions between coils during robotic operation.

## Motivation
Traditional Transcranial Magnetic Stimulation (TMS) allows the study or modulation of a single brain region at a time. However, complex brain functions and neurological conditions emerge from the interaction between multiple areas that form a network. Limiting one stimulation point prevents direct investigation of these dynamics.

The need for a dual-site TMS tool arises to overcome this barrier, allowing:

- Mapping network dynamics: Investigating how activity in one brain region directly influences another, revealing the causality and strength of neural connections in real time.

- Developing new therapies: Modulating dysfunctional neural networks more fully.

- Understanding complex functions: Studying how different brain centers cooperate to perform tasks.

## Features Implemented
### Feature 1:  Improvements in multiple coil mode
To increase flexibility and improve clarity in coil identification, we've introduced the option to name coils, making it possible to associate coil targets with a single coil.

- #### Coil name 

There are two ways to change the coil name:

  - Coil registration window: In the coil selection box for registration, you can change the name. The displayed sequence of coils follows the same sequence as the markers added when connecting to the tracker.

  - Coil selection panel: By right-clicking on the coil you can change its name.

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/object_calibration_dialog.png" width="800" height="400"/>


### Feature 2 : Better User Feedback and Error Handling
Success messages were added for completed exports and clear error messages for issues like:
- Empty surface data.
- Permission problems.
- Unsupported file types.
- If the GUI is not available (e.g., running in headless mode), the system falls back to simple console messages instead of crashing.

### Feature 3: Simulated Progress for VTK-Based Writers
VTK’s built-in writers (e.g., vtkSTLWriter, vtkPLYWriter, vtkXMLPolyDataWriter) do not provide native support for progress updates. To work around this, I implemented a simulated progress mechanism that estimates export progress based on the number of points and a configurable update interval.

These updates don’t track the actual write process, but by estimating progress based on the number of points, they help give users a sense that the export is moving forward. This makes the application feel responsive, even during longer operations.

![image](https://github.com/user-attachments/assets/64361cf4-8085-475b-9ae7-5856d32fe0ee)



### Feature 4: Extended Format Support and Cleaner Workflow
- Preserved existing polydata export functionality for STL, PLY, VTP, etc.
- Extended progress feedback system to full 3D scene exports for formats like RIB, VRML, X3D, OBJ, and IV.
- Ensured backward compatibility and integration with existing workflow.

### Feature 5: Refactored Export Workflow
Previously, the export logic was scattered and difficult to extend.
I refactored _export_surface() in surface.py to:
- Group common tasks (e.g., polydata preparation, normal orientation).
- Centralize progress updates and cancellation checks.
- Make the workflow cleaner and easier to maintain for future extensions.


## Weekly Reports
👉 [Community Bonding Period](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Community%20Bonding%20Period.md) 

👉 [Week-1](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-1.md) -- [Week-2](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-2.md) -- [Week-3](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-3.md) -- [Week-4](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-4.md) --[Week-5](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-5.md)

👉 [Week-6](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-6.md) -- [Week-7](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-7.md) -- [Week-8](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-8.md) -- [Week-9](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-9.md) -- [Week-10](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-10.md)

👉 [Week-11](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-11.md) -- [Week-12](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-12.md) -- [Week-13](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-13.md) -- [Week-14](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-14.md)


## Project Status

The project is 100% complete and successfully merged into the main repository.  
All planned features have been implemented, tested, reviewed, and accepted.

- **Pull Request (Merged):** [#994 – Added progress bar for 3D surface exports](https://github.com/invesalius/invesalius3/pull)  
- **Related Issue:** [#991 – Add progress bar to export 3D surface](https://github.com/invesalius/invesalius3/issues)

  This contribution is now part of the official InVesalius codebase.



## Challenges Faced

- **Maintaining Existing Functionality**  
  While adding progress dialogs, I had to ensure that no existing export formats broke or behaved unexpectedly.

- **Simulating Progress for VTK Writers**  
  VTK does not support native progress tracking, so I implemented a simulation using loop-based updates over surface points.

- **Handling Export Cancellation**  
  Initially, files were still being saved even after cancellation. I added checks and cleanup logic to prevent incomplete exports.

- **Auto-Closing Progress Dialog**  
  Ensured the progress dialog closed automatically after success or cancellation, improving overall user experience.

## Acknowledgements

I sincerely thank my mentors **Renan Matsuda**, **Victor Malheiro**, **Thais Marchetti** and **Lucas Betioli**, for there continuous guidance, support, and valuable feedback throughout the project. His guidance played a vital role in shaping my GSoC journey.
I also extend my gratitude to the organization admin **Renan Matsuda**, mentor **Thiago F Moraes** and the entire [**InVesalius**](https://github.com/invesalius) community for being part of this journey and facilitating a smooth and supportive GSoC experience.

Contributing to an open-source medical imaging project as part of Google Summer of Code 2025 has been a transformative experience for me. I gained practical experience with large codebases, learned how to write robust and user-friendly features, and developed a deeper appreciation for open-source development and collaboration.

Special thanks to **Google Summer of Code** for providing this incredible opportunity to contribute to open source and grow as a developer.