cmake_minimum_required(VERSION 2.8.3)
project(vulcano_torso_control)

find_package(catkin REQUIRED COMPONENTS
  robot_state_publisher
  controller_manager
  controller_manager_msgs
)

catkin_package()

install(DIRECTORY config launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
