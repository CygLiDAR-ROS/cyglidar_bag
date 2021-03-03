cmake_minimum_required(VERSION 2.8.3)

set(PROJECTNAME "cyglidar_rosbag")
project(${PROJECTNAME} CXX C)

set(extra_flags -std=c++11 -Werror -Wall -Wextra)
set(CMAKE_CXX_FLGAS "${CMAKE_CXX_FLAGS} ${extra_flags}")
set(CMAKE_C_LINK_EXECUTABLE ${CMAKE_CXX_LINK_EXECUTABLE})

add_compile_options(-std=c++11)

add_definitions(${COMPILE_FLAGS} ${PCL_DEFINITIONS})
add_definitions(-Wall -O2)

find_package(Boost REQUIRED COMPONENTS system)
find_package(PCL 1.2 REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  rospy
  roscpp
  sensor_msgs
  message_filters
  std_msgs
  genmsg
  tf
)

generate_messages(DEPENDENCIES std_msgs)

link_directories(${PCL_LIBRARY_DIRS})

install(DIRECTORY include/${PROJECT_NAME}/
    DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
    FILES_MATCHING PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)

install(DIRECTORY launch/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
  PATTERN ".svn" EXCLUDE)

install(DIRECTORY rosbag
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
