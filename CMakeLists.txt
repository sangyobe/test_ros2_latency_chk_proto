cmake_minimum_required(VERSION 3.8)
project(latency_chk_proto)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

# generate interfaces
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/LatencyCheckRequest.msg"
  "msg/LatencyCheckPayload.msg"
  "srv/LatencyCheck.srv"
  DEPENDENCIES std_msgs
)

ament_package()
