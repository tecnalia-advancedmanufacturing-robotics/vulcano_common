cmake_minimum_required(VERSION 2.8.3)
project(vulcano_calibrated_ur_description)

find_package(catkin REQUIRED COMPONENTS
  ur_description
)

catkin_package()

install(DIRECTORY urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
