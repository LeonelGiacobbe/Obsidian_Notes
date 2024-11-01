<mark style="background: #FF5582A6;">Remember to</mark> `#include <moveit_visual_tools/moveit_visual_tools.h>`

Simplest user interface for MoveIt. 
- Create Motion plans
- Moving bot 
- Adding objects to environment


### Creating an interface
```c++
// Create the MoveIt MoveGroup Interface

  using moveit::planning_interface::MoveGroupInterface;

  auto move_group_interface = MoveGroupInterface(node, "NameOfPlanningGroup");
```

### Adding and removing collision objects 
Done with [[PlanningSceneInterface]].
```c++
moveit::planning_interface::PlanningSceneInterface planning_scene_interface;
```