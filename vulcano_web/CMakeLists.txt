cmake_minimum_required(VERSION 2.8.3)
project(vulcano_web)

find_package(catkin REQUIRED COMPONENTS
  message_runtime
  std_srvs
  std_msgs
  tf
  message_generation
  cv_bridge
)

catkin_python_setup()

add_service_files(
  FILES
  RecordVideo.srv
  set_controller_options.srv
  get_controller_options.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS roscpp rospy std_msgs
  DEPENDS system_lib python-serial python-sys
)

install(
  DIRECTORY css_files images javascript_libraries launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
