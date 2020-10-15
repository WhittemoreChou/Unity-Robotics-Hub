# Pick and Place Tutorial [DRAFT]

Placeholder introduction. This document breaks down the current status of Jacob & Jonathan’s Pick & Place demo into smaller tutorials that start from scratch (with provided assets). 

## [Step 1: Create Unity scene with imported UR3 URDF](1_urdf.md)

Assumptions: ?

By the end of this tutorial: User should have Unity Hub and Unity 2020.2+ installed with a basic sensical scene setup, including a static floor and table, as well as the cube and UR3 articulation arm. 

Verification: Pressing Play in the editor does nothing and throws no errors, the scene has proper setup (e.g. gravity, colliders), and lengths of the articulation body can be highlighted with arrow keys via the built-in URDF importer
 
 ## [Step 2: Unity & ROS Integration](2_ros_tcp.md)
 
Assumptions: Previous steps have been completed (Unity environment). Access to a ROS workspace. Basic understanding of C#.

By the end of this tutorial: The TCP connection between Unity & ROS is functioning. The C# scripts have been generated from the relevant .msg files. The cube pose is successfully published as a ROS topic. The server_endpoint.py runs as expected.

Verification: Running rostopic echo ur3_topic will successfully find the published pose of the static cube and print it.
 
## [Step 3: Naive Pick & Place](3_naive.md)
 
Assumptions: Previous steps have been completed. Basic understanding of Python.

By the end of this tutorial: All the necessary dependencies have been installed for moveit, rospy. The C# script for MotionPlanningService is generated. Base ur3_gripper_motion_planning_script script and MotionPlanningService/GripperController correctly run a pick & place.

Verification: The necessary processes can be roslaunch-ed with no unexpected errors. Playing the Unity scene will make a TCP connection, send the cube pose, move the arm to the set initial position, prompt the motion planning, and receive the calculated trajectory. The arm will pick & place the cube.


**[Continue to Phase 1: Setup and Basic Randomizations](1_urdf.md)**