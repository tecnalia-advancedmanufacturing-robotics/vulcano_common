cmake_minimum_required(VERSION 2.8.3)
project(vulcano_description)

find_package(catkin REQUIRED COMPONENTS
  message_runtime
#  vulcano_base_description
  vulcano_torso_description
  std_msgs
  std_srvs
  tf
)

catkin_package()

install(DIRECTORY launch robots
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
