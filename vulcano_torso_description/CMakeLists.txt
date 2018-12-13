cmake_minimum_required(VERSION 2.8.3)
project(vulcano_torso_description)

find_package(catkin REQUIRED COMPONENTS
  message_runtime
  std_msgs
  std_srvs
  tf
#  robotnik_msgs
)

catkin_package()

install(DIRECTORY launch meshes robots urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
