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

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/object_calibration_dialog.png" width="320" height="400"/>
<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/change_coil_name.png" width="640" height="400"/>

- #### Coil targets associated with the coil

With a registered coil selection box in the navigation panel, you can define who will be creating the coil targets, and you can check the coil displayed along with its coil target in the markers panel. You can also change which coil is associated by right-clicking on the coil target of interest.

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/change_coil_associated.png" width="636" height="400"/>

### Feature 2 : Connection with two robots

The robots are controlled through an external repository (tms-robot-control) and communicate with Invesalius through the local server. To control both robots, a message splitter was added to the server for both instances of robot control objects, using the robot ID. Additionally, to allow dual robot control, a second robot connection and registration setting was added to the Invesalius preferences window, and a second set of robot control buttons was added to the navigation panel with an additional button for resetting robot errors.

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/dual_robot.png" width="636" height="400"/>

Each robot must be associated with a single coil, otherwise this is done in the preferences window on the TMS coil tab.

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/robot_coil_selection.png" width="300" height="400"/>

### Feature 3: Double simultaneous navigation
Simultaneous navigation can be activated from a button on the navigation panel with the multiple-target icon. When activated, it adds a second screen that allows for two independent scenes, and it becomes possible to set more than one target, respecting one per coil. Navigation windows are associated with a single coil, and you can verify which one it is by the title.

The image plan windows are disabled and the coil display indicators by the tracking device have been changed to display small spheres that represent each coil, changing their colors to the display status.

<img src="https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/images/simultaneous_navigation.png" width="636" height="400"/>

### Feature 4: Robot collision algorithm
An efficient solution proposed to avoid coil collisions considered the dynamic alteration of the robot's motion coefficient based on the distances between the coils. To achieve this, the coils were considered a sphere, and beyond a certain distance, the coils decrease their speeds exponentially. The coefficients associated with the mathematical model took into account the sphere's radius, which is related to the coil's size, and the exponential decay coefficient, which was chosen empirically. Although the algorithm is functional, improvements are still needed to avoid collisions between the robots and to ensure proper coil geometry.

## Weekly Reports
👉 [Community Bonding Period](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Community%20Bonding%20Period.md) 

👉 [Week-1](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-1.md) -- [Week-2](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-2.md) -- [Week-3](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-3.md) -- [Week-4](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-4.md) --[Week-5](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-5.md)

👉 [Week-6](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-6.md) -- [Week-7](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-7.md) -- [Week-8](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-8.md) -- [Week-9](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-9.md) -- [Week-10](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-10.md)

👉 [Week-11](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-11.md) -- [Week-12](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-12.md) -- [Week-13](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-13.md) -- [Week-14](https://github.com/MarcioCamposJr/Google-Summer-of-Code-2025-Final-Report/blob/main/Weekly%20Reports/Week-14.md)


## Next steps

- #### Simultaneous navigation with 4 coils
    To increase the number of reels browsed simultaneously, it would be possible to divide them into up to 4 navigation windows and bring a layout control for viewing, such as setting the reels of interest and switching between possible viewing configurations.
- #### Drag and drop navigation window system
    To increase the size of the viewing window and be able to see more than one window simultaneously, it would be interesting to create navigation windows that could be dragged to other monitors.
- #### Improvement in collision algorithm
    A more robust collision algorithm model can be implemented considering repulsion in strategic regions, minimizing collision between the robotic arms and the coils and maximizing the positioning possibilities of the two coils.
## Project Status

The project is functional, but improvements to the collision algorithm would allow for greater freedom in coil positioning. The pull request is still under review, but fixes have already been proposed and implemented, constituting a step toward merging with the main branch.

- **Pull Request (Merged):** [#994 – Added progress bar for 3D surface exports](https://github.com/invesalius/invesalius3/pull)  


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