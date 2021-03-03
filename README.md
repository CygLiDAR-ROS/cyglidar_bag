# cyglidar_rosbag
cyglidar_rosbag is a ROS package built to see how CygLiDAR works on rviz.
This repository contains ROSBAG sample data, launch files and the octomap_mapping package to play the bag file(s).

## Prerequisites
- Ubuntu 18.04
- ROS Melodic

## Download
Copy both hector_mapping and octomap_mapping packages to your catkin workspace as follows:
```bash
git clone https://github.com/tu-darmstadt-ros-pkg/hector_slam.git -b melodic-devel
```
```bash
git clone https://github.com/ros/ros_comm.git -b melodic-devel
```
