# -autonomous_navigation_wss
10666785 ID_autonomous_nav Module Leader: Dr Mario Gianni



1. Installation of Package
    • Extract the package.
    • Place the "kobuki" package to your workspace/src (if your workspace name is catkin_ws then you need to replace "workspace" by "catkin_ws") .
    • Open the terminal and use the commands below with the sequence.
    i. cd workspace
    ii. catkin_make
    iii. source devel/setup.bash

2.  2D Simultaneous Localization and Mapping (SLAM)
    (a) Open the terminal and type the commands below.
roslaunch turtlebot_gazebo turtlebot_world.launch

    (b) Open another terminal and write the following command.
roslaunch turtlebot_navigation gmapping_demo.launch

    (c) Open another terminal and write.
 roslaunch turtlebot_teleop keyboard_teleop.launch

    (d) Now move the robot in the environment via keyboard keys. once the map is completed then save it using the following command after opening a new terminal.

rosrun map_server map_saver -f /home/fly /catkin_ws/src/kobuki/turtlebot_apps/turtlebot_navigation/maps/mape

You have to provide the exact location where you want to save your map according to the directories your laptop has.
"mape" is the name of your map  (you can name it by yourself).

    (e) Close the gmapping terminal.

    (f) Now it is time to localize the robot.
use the following command.
roslaunch turtlebot_navigation amcl_demo.launch map_file:=/home/fly /catkin_ws/src/kobuki/turtlebot_apps/turtlebot_navigation/maps/mape.yaml

    (g) Now we are providing the same map that we saved in the previous step.
    (h)  Localization.

2D Pose Estimate :
In this method you have to select 2D pose estimate in rviz and the click on the exact location of robot in rviz.
Teleop keys :
Now move the robot in the environment via keyboard keys.


3.  PTP-PP algorithm
    (a) Open the terminal and type the commands below.
roslaunch turtlebot_gazebo turtlebot_world.launch

    (b) use the following command.
roslaunch turtlebot_navigation amcl_demo.launch map_file:=/home/fly /catkin_ws/src/kobuki/turtlebot_apps/turtlebot_navigation/maps/mape.yaml

    (c) Open another terminal and write.
 roslaunch turtlebot_teleop keyboard_teleop.launch

	now move your robot in the world. So that robot localize itself.

    (d)  Now you have to select the 2D goal in rviz and click anywhere the will go there.


