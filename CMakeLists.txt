cmake_minimum_required(VERSION 3.8)
project(ftd_master_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
#find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)

# Specify the message files to be built
set(msg_files
  "msg/PoseStampedWithTaskId.msg"
)

# Generate message interfaces
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs geometry_msgs #builtin_interfaces # Required for PoseStamped and String types
)

ament_package()

