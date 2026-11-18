cmake_minimum_required(VERSION 3.8)
project(swarmtal_msgs)

find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/DronePosCtrlCmd.msg"
  "msg/DronePosControlState.msg"
  "msg/DroneCommanderState.msg"
  "msg/DroneOnboardCommand.msg"
  DEPENDENCIES geometry_msgs sensor_msgs std_msgs
)

ament_export_dependencies(geometry_msgs rosidl_default_runtime sensor_msgs std_msgs)
ament_package()
