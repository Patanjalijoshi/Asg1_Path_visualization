Trajectory Visualization and Storage ROS Package

This ROS package provides functionality for visualizing and storing trajectory data generated by an autonomous mobile robot (AMR). It consists of two main nodes:

    Trajectory Publisher and Saver Node: This node collects the robot's trajectory path as it moves through the environment. It formats the trajectory data as a marker array and publishes it for visualization. Additionally, it implements a ROS service handler to handle requests for saving trajectory data to a file, allowing users to specify a time duration to save the trajectory data.

    Trajectory Reader and Publisher Node: This node reads the saved trajectory file, transforms the trajectory data to the odom frame, and publishes it as a marker array for visualization.

Features

    Collects trajectory data from an AMR.
    Formats trajectory data as a marker array for visualization in RViz.
    Saves trajectory data to a file upon request, with the ability to specify a time duration.
    Reads saved trajectory data from a file and publishes it for visualization.

 Limitations
    Haven't tested edge cases like keeping the data collection running for large span of time 



How to run the code:
As shown in the assignment document using the AR100 package
http://wiki.ros.org/AnscerRobotics/AR100

1. roslaunch start_anscer start_anscer.launch
2. roslaunch anscer_navigation anscer_navigation.launch map_name:=anscer_map 

In the work space where the repo is cloned
1. rosrun my_cpp_package trajectory_saver_publisher_node 
2. rosservice call /save_trajectory "my_trajectory.csv" 5   {passing file name and duration }
3. rosrun my_cpp_package trajectory_reader_publisher_node my_trajectory.csv   {passing the file name} 


