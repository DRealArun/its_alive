cmake_minimum_required(VERSION 3.10.0)
project(traverser)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
    roscpp
    rospy
    robot_common
    gazebo_dev
    gazebo_msgs
    geometry_msgs
    sensor_msgs
    nav_msgs
    std_msgs
    tf
)

catkin_package(
)

find_package(Boost REQUIRED COMPONENTS thread)

include_directories(
    ${Boost_INCLUDE_DIRS}
    ${catkin_INCLUDE_DIRS}
    ${GAZEBO_INCLUDE_DIRS}
)


####################################
# TRAVERSER CONTROLLER GAZEBO PLUGIN
####################################
add_library(traverser_controller_plugin
    plugin/traverser_controller_plugin.cpp
)
target_link_libraries(traverser_controller_plugin
    ${catkin_LIBRARIES}
    ${GAZEBO_LIBRARIES}
    ${Boost_LIBRARIES}
)
