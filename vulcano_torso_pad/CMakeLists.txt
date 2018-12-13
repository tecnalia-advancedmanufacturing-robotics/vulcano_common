cmake_minimum_required(VERSION 2.8.3)
project(vulcano_torso_pad)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs
  nav_msgs
  robotnik_msgs
  roscpp
  sensor_msgs
  diagnostic_updater
)

catkin_package(
  CATKIN_DEPENDS
    nav_msgs
    robotnik_msgs
    roscpp
    sensor_msgs
    geometry_msgs
    message_runtime
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

# For debugging via Qt Creator
SET(CMAKE_BUILD_TYPE Debug)

add_executable(vulcano_torso_pad src/vulcano_torso_pad.cpp)

add_dependencies(vulcano_torso_pad robotnik_msgs_generate_messages_cpp)

target_link_libraries(vulcano_torso_pad
   ${catkin_LIBRARIES}
)

install(TARGETS vulcano_torso_pad
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY config launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
