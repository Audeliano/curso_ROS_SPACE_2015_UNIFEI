cmake_minimum_required(VERSION 2.8.3)
project(rosaria_motion)

find_package(catkin REQUIRED COMPONENTS
	roscpp
)

catkin_package(
	CATKIN_DEPENDS
)

include_directories(
	include
	${catkin_INCLUDE_DIRS}
)

add_executable(rosaria_motion_node 
	src/rosaria_motion_node.cpp
	src/RosariaMotionNode.cpp
)

add_dependencies(rosaria_motion_node 
	${catkin_EXPORTED_TARGETS}
)

target_link_libraries(rosaria_motion_node
	${catkin_LIBRARIES}
)

add_executable(rosaria_motion_client_node 
	src/rosaria_motion_client_node.cpp
)

add_dependencies(rosaria_motion_client_node 
	${catkin_EXPORTED_TARGETS}
)

target_link_libraries(rosaria_motion_client_node
	${catkin_LIBRARIES}
)
