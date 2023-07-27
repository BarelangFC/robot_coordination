cmake_minimum_required(VERSION 3.5)
project(robot_coordination)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(bfc_msgs REQUIRED)

include_directories(include)

add_executable(robot_coordination src/robot_coordination.cpp)
ament_target_dependencies(robot_coordination rclcpp std_msgs bfc_msgs)

install(TARGETS
  robot_coordination
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
