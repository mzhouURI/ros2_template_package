cmake_minimum_required(VERSION 3.5)
project(behavior_interface)

find_package(ament_cmake REQUIRED)
find_package(mvp2_common REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rclcpp_lifecycle REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(pluginlib REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(tf2_ros REQUIRED)
find_package(mvp2_util REQUIRED)
find_package(mvp_msgs REQUIRED)

mvp2_package()

set(dependencies
  rclcpp
  rclcpp_lifecycle
  std_msgs
  geometry_msgs
  pluginlib
  nav_msgs
  tf2_ros
  mvp_msgs
)

install(DIRECTORY include/
  DESTINATION include/
)

# if(BUILD_TESTING)
#   find_package(ament_lint_auto REQUIRED)
#   # the following line skips the linter which checks for copyrights
#   set(ament_cmake_copyright_FOUND TRUE)
#   ament_lint_auto_find_test_dependencies()
# endif()

ament_export_include_directories(include)
ament_export_dependencies(${dependencies})

ament_package()
