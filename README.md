[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
---
# turtlebot_rl
## Introduction
Simple obstacle avoidance algorithm for TurtleBot3 with Lidar

<p align="center">
<img src="result/Test_2.gif"/>
</p>

<p align="center">
<img src="result/Test_3.gif"/>
</p>

## Assumptions/Dependencies
ROS Melodic

## Gazebo Simulation Map
Custom world used
 - worlds/map.world (can be updated in launch file)

## Building the package
1) Create a catkin workspace catkin_ws

2) Create src direcory and clone the turlebot3 package inside catkin_ws/src using 

``` 
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git   
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git    
```
Refer this [link](https://automaticaddison.com/how-to-launch-the-turtlebot3-simulation-with-ros/).

4) Clone the turtlebot_rl package
```
git clone https://github.com/siddharthtelang/turtlebot_rl.git

```
4) Go back to catkin_ws
```
cd catkin_ws
```
5) compile 

``` 
catkin build 
```

## How to run the code

1) Source the workspace (every new terminal)

```
source devel/setup.bash
```

2) Launch the launchfile

```
roslaunch turtlebot_rl walker_avoid_obstacle.launch
```

3) User Operated (Teleop)
```
roslaunch turtlebot3_gazebo turtlebot3_stage_4.launch
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

3) With ROSBag enabled
 - update the directory argument in launch file rosbag_directory
```
roslaunch turtlebot_rl walker_avoid_obstacle.launch record_bag:=true rosbag_directory:='/home/siddharth/ENPM808X/catkin/src/turtlebot_rl/rosbag'
```


## Recording the bag file
- Set the record_bag param true in the launch file or while launching the launch file


## Recording bag file through command line
```
rosbag record -a -x '(.*)/camera(.*)' -O record_bag.bag -a --duration 30
```

## Running the bag file
```
rosbag play <bagfile_name> --pause
```

## Bag file and test videos
https://drive.google.com/drive/folders/1snH6yK4TECaIBBCA1JaZIra0Roafp13m?usp=sharing
