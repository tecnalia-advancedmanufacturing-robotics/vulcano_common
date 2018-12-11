cmake_minimum_required(VERSION 2.8.3)
project(vulcano_base_navigation)

find_package(catkin REQUIRED COMPONENTS
	message_runtime
	std_msgs
	move_base
	gmapping
	amcl
)

catkin_package()

install(DIRECTORY config_navigation config_rviz launch maps scripts
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
