##Le package SMA_leader-follower contient les fichiers essentiels pour faire le leader-follower avec deux turtleBot3 en simulation
#Pour lancer la simulation utiliser les commandes suivantes:

cd catkin_ws/src
cd ..
catkin_make
roslaunch sma_leader-follower lead-follow.launch

rosrun map_server map_server ~/map.yaml

roslaunch sma_leader-follower amcl_tb0.launch

roslaunch sma_leader-follower amcl_tb1.launch

rosservice call /tb3_0/request_nomotion_update 

rosservice call /tb3_1/request_nomotion_update

roslaunch sma_leader-follower multi_rviz.launch

rosrun sma_leader-follower leader_follower.py

ROS_NAMESPACE=tb3_0 rosrun turtlebot3_teleop turtlebot3_teleop_key

