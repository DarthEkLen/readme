<p align="justify">
  <h1>Simulation of DUM-E</h1>
</p>

In the project Dum-E, the simulation are done with the help of MATLAB and Simulink.
In this project, our robot Dum-E performs simple task of pick and place using a cad model Kinova Gen 3 Manipulator. <br>

The cad Model, [Kinova Gen 3](https://www.kinovarobotics.com/en/products/gen3-robot) is imported directly to be used in the simulation.

To perform the task, Environment is created to place shelves, balls and blocks for the robot so that pick and place task is performed.<br>
The final video for the simulation is in the Images and Video Folder. the simulations are then run to identify the object and place it to<br>
the desired position. The Instructions for the same are below.<br>

# Instructions
Import robot
 ```
 robot = loadrobot('kinovaGen3', 'DataFormat', 'column');
 ```
 [Build World](https://github.com/rodion0917/DumE/blob/main/src/example_Command_Build_World.m) <br>
 This command help create the shelves, blocks and the spheres so that pick and place task can be comnputed.
 
 [Detect Parts](https://github.com/rodion0917/DumE/blob/main/src/example_Command_Detect_Parts.m) <br>
 This function detects parts using a list in the coordinator that also provides the pose.
 
 [Classify Parts](https://github.com/rodion0917/DumE/blob/main/src/example_Command_Classify_Parts.m) <br>
 This step helps classify the parts to determine where to place them.
 
 [Plan Execute Trajactory](https://github.com/rodion0917/DumE/blob/main/src/example_Helper_Plan_Execute_Trajectory_Pick_Place.m) <br>
 This function generates a collision-free trajectory between an initial configuration given by JOINTINIT <br> 
 and a target task-space orientation, provided by TASKFINAL.
 
 [HelperCoordinatorPickPlace](https://github.com/rodion0917/DumE/blob/main/src/example_Helper_Coordinator_Pick_Place.m) <br>
 This class is used to control the pick-and-place workflow execution.
 
 [Activate/Deactivate Gripper](https://github.com/rodion0917/DumE/blob/main/src/example_Command_Activate_Gripper.m) <br>
 This command activates and deactivates the gripper. It has 2 effects:<br>
 1. When the gripper is activated, the picked part is added as a collision mesh to the robot rigid body tree so that path<br>
    planning includes the part in the obstacle avoidance stage. When deactivating the gripper, the placed part is removed <br>
    from the collision meshes of the rigid body tree.
 2. The visualization is updated to move the object being picked up by the gripper. 
 
 [Compute Grasp Pose](https://github.com/rodion0917/DumE/blob/main/src/example_Command_Compute_Grasp_Pose.m) <br>
 This command computes the task-space grasping pose required for the manipulator to pick up a part.

#yaha se naye include ho rahe








