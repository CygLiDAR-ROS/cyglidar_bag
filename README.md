# cyglidar_rosbag
cyglidar_rosbag is a ROS package built to see how CygLiDAR works on rviz.
This repository contains launch files and the octomap_mapping package to play the bag files.

## Prerequisites
- Ubuntu 18.04
- ROS Melodic

## Download
First, copy both hector_mapping and octomap_mapping packages to your catkin workspace as follows:
```bash
$ git clone https://github.com/tu-darmstadt-ros-pkg/hector_slam.git -b melodic-devel
```
```bash
$ git clone https://github.com/ros/ros_comm.git -b melodic-devel
```
Then, download ROSBAG sample data from the following page:
https://drive.google.com/file/d/1dN4ll4EzpHoalbpheoFlR-CizD0ZT2RK/view?usp=sharing
The bag file should be moved into **src/cyglidar_bag/cyglidar_rosbag/rosbag** directory.

## Run
Run slam packages with a launch file as below:
1) Terminal 1
```bash
$ roslaunch cyglidar_rosbag cyglidar_rosbag.launch
```
2) Terminal 2
Play the recorded ROSBAG file.
```bash
$ cd src/cyglidar_bag/cyglidar_rosbag/rosbag
$ rosbag play --clock 210303_cyglidar.bag
```
