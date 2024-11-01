When planning movements for the Kinova Gen3, the starting pose is calculated based on sensor values, and only the target pose needs to be declared.

```c++
auto const target_pose = [] {
  geometry_msgs::msg::Pose msg;
  msg.orientation.y = 0.0;
  msg.orientation.w = 0.0;
  msg.position.x = 0.1;
  msg.position.y = 0.4;
  msg.position.z = 0.4;
  return msg;
}();
move_group_interface.setPoseTarget(target_pose);
```