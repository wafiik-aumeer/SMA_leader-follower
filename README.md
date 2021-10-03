
cd catkin_ws/src

git clone https://github.com/Goohuram/sma_twoturtle.git

cd ..

catkin_make


roslaunch sma_twoturtle two_in_turtle_world.launch

rosrun map_server map_server ~/map.yaml

roslaunch sma_twoturtle amcl_tb0.launch

roslaunch sma_twoturtle amcl_tb1.launch

rosservice call /tb3_0/request_nomotion_update 

rosservice call /tb3_1/request_nomotion_update

roslaunch sma_twoturtle multi_rviz.launch

rosrun sma_twoturtle leader_follower.py

ROS_NAMESPACE=tb3_0 rosrun turtlebot3_teleop turtlebot3_teleop_key

