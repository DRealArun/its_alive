cmake_minimum_required(VERSION 3.10.0)
project(traverser)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
    roscpp
    rospy
    robot_common
)

catkin_package(
)