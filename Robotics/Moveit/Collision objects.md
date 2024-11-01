<mark style="background: #FF5582A6;">Remember to</mark> `#include <moveit/planning_scene_interface/planning_scene_interface.h>`

### Creating a collision object 
```c++
auto const collision_object = [frame_id =
                                 move_group_interface.getPlanningFrame()] {
  moveit_msgs::msg::CollisionObject collision_object;
  collision_object.header.frame_id = frame_id;
  collision_object.id = "box1";
  shape_msgs::msg::SolidPrimitive primitive;
```
-  Same `frame_id` as the robot's. `move_group_interface.getPlanningFrame`, where `move_group_interface` is the name of the [[MoveGroupInterface]] object.
- Create a `CollisionObject` message with attributes `header.frame_id` and `id`

Then we define the dimensions of the object 
```c++
 // Define the size of the box in meters
  primitive.type = primitive.BOX;// can be BOX, CYLINDER, SPHERE or CONE
  primitive.dimensions.resize(3);
  primitive.dimensions[primitive.BOX_X] = 0.5;
  primitive.dimensions[primitive.BOX_Y] = 0.1;
  primitive.dimensions[primitive.BOX_Z] = 0.5;
```

Then the pose (location and rotation) of the object 
```c++
// Define the pose of the box (relative to the frame_id)

  geometry_msgs::msg::Pose box_pose;

  box_pose.orientation.w = 1.0;  // We can leave out the x, y, and z components of the quaternion since they are initialized to 0

  box_pose.position.x = 0.2;

  box_pose.position.y = 0.2;

  box_pose.position.z = 0.25;
```
Lastly, we add `primitive` to the `collisionObject` we declared in the first code box.
```c++
collision_object.primitives.push_back(primitive);
// Save tuned pose of box
collision_object.primitive_poses.push_back(box_pose);
// Add object with shape, dimensions and pose to the scene
collision_object.operation = collision_object.ADD;
```

### Adding object to planning scene 
```c++
// Add the collision object to the scene
moveit::planning_interface::PlanningSceneInterface planning_scene_interface;
planning_scene_interface.applyCollisionObject(collision_object);
//collision_object is the name of the CollisionObject msg declared above
```