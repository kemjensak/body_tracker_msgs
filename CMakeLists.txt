cmake_minimum_required(VERSION 3.8)
project(body_tracker_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/BodyTracker.msg"
  "msg/BodyTrackerArray.msg"
  "msg/Skeleton.msg"
  DEPENDENCIES
    geometry_msgs
    std_msgs)

install(TARGETS
  DESTINATION lib/${PROJECT_NAME})

ament_package()