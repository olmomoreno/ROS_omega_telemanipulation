# What version of CMake is needed?
cmake_minimum_required(VERSION 2.8.3)

# The name of this package.
project(omega_telemanipulation)

# Find the catkin build system, and any other packages on which we depend.
find_package(catkin REQUIRED COMPONENTS roscpp visualization_msgs)

# Declare our catkin package.
catkin_package()

# Specify locations of header files.
include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(marker_array_telemanipulation_exe src/macs_telemanipulation.cpp)
target_link_libraries(marker_array_telemanipulation_exe ${catkin_LIBRARIES})

add_executable(collision_engine_omega_telemanipulation_exe src/collision_engine_omega_telemanipulation.cpp)
target_link_libraries(collision_engine_omega_telemanipulation_exe ${catkin_LIBRARIES})

link_directories(/home/olmo/jade_workspace/src/omega_telemanipulation/libraries) 
add_executable(omega_engine_telemanipulation_exe src/omega_engine_telemanipulation.cpp)
target_link_libraries(omega_engine_telemanipulation_exe dhd usb-1.0)
target_link_libraries(omega_engine_telemanipulation_exe ${catkin_LIBRARIES})


