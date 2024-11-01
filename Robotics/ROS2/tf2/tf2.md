---
Status: Not started
Nav2: false
---
> [!important]  
> Frames are defined using the right hand rule, with Z up and X forward, and units should be standard SI units (meters for translations, radians for rotations).  

# ==What it does==

Tf2 allows us to keep track of all reference frames inside a simulation, as well as the relationships between these frames (distance between them, offset angle, etc).

Nav2 requires the following transformations to be published in ROS2:

1. `map` => `odom`
2. `odom` => `base_link`
3. `base_link` => `base_laser` (sensor base frames. Camera, lidar, etc)

# ==The tf2 tree==

The tf2 frame structure resembles that of a tree, not a closed loop. It is structurally very similar to that of [[(Nav2) Behavior Trees]]. A frame can only have **one** parent, but can have **multiple** children.

To view the transform between a parent and a child:

`ros2 run tf2_ros tf2_echo parent_name child_name`

  

# ==Unified Robot Description Format (URDF)==

The URDF is an XML file that is used for multiple things, including setting up transforms between the different parts of a robot, and also visualizing the state of a robot in rviz.

# ==Rviz and tf2==

Rviz is a visualization tool that can be used to see the relationships between the frames set up by tf2.

# ==Writing a simple transform==

The basic syntax for a parent-child transform is:

`ros2 run tf2_ros static_transform_publisher cx cy cz px py pz parent_name child_name`

Let’s say we have two frames, `base_link` and `base_laser`. Let’s also assume that, in this robot, `base_laser` is 10 centimeters above and 20 centimeters ahead of `base_link`.(example: `base_laser = (0.1 0 0.2)`, and `base_link = (0.0, 0.0, 0.0)`.

If we wanted to create a transform between the two, we would need to do:

`ros2 run tf2_ros static_transform_publisher 0.1 0 0.2 0 0 0 base_link base_laser`

  

# ==Writing a fixed frame broadcaster==

[[Example code]]

### Important imports:

```Python
from geometry_msgs.msg import TransformStamped

import rclpy
from rclpy.node import Node

from tf2_ros import TransformBroadcaster
```

  

### Creating a parent and child transform (inside of a method that belongs to an rclpy [[Nodes (Python)]] class):

```Python
t = TransformStamped()

t.header.stamp = self.get_clock().now().to_msg()
t.header.frame_id = 'parent1'
t.child_frame_id = 'child1'
t.transform.translation.x = 0.0
t.transform.translation.y = 2.0
t.transform.translation.z = 0.0
```

In the code above, we create an object `t` of type `transformStamped` (see imports above).

- `t.header.stamp`:
- `t.header.frame_id`: this line creates an ID for the **parent** reference.
- `t.child_frame_id`: this line creates an ID for the **child** reference.
- `t.transform.translation`: the last three lines determine the positional transformation between the parent and the child reference. In this case, the child reference is moved 2 meters across the Y-axis.

`transform.translation` refers to a change in **distance**.

`transform.rotation` refers to a change in **rotation**

> [!important]  
> NOTE: coordinates are NOT absolute, they are in relationship between parent-child. In this case, this means that if the parent is at (50.0,10.0,0.0) the child will be at (50.0,12.0,0.0)