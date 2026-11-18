cmake_minimum_required(VERSION 3.8)
project(swarm_msgs)

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(lcm CONFIG REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(tf2 REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/DPGOData.msg"
  "msg/DPGOSignal.msg"
  "msg/DroneTraj.msg"
  "msg/ImageArrayDescriptor.msg"
  "msg/ImageDescriptor.msg"
  "msg/Landmark.msg"
  "msg/LoopEdge.msg"
  "msg/LoopEdges.msg"
  "msg/NodeDetected.msg"
  "msg/NodeDetectedXyzyaw.msg"
  "msg/NodeFrame.msg"
  "msg/SwarmFused.msg"
  "msg/VIOFrame.msg"
  DEPENDENCIES builtin_interfaces geometry_msgs nav_msgs std_msgs
)

install(DIRECTORY include/ DESTINATION include/${PROJECT_NAME})
ament_export_include_directories(include)
ament_export_dependencies(builtin_interfaces geometry_msgs lcm nav_msgs rclcpp
  rosidl_default_runtime std_msgs tf2)
ament_package()
