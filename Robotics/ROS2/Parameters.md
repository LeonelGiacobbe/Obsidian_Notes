---
Status: Not started
Nav2: false
---
You can think of a parameter as the “settings” of [[Nodes]]. To see the  
parameters belonging to nodes:  

- `ros2 param list`

To see a parameter’s type:

- `ros2 param get`

To change the value of a parameter:

- `ros2 param set <node_name> <parameter_name> <value>`
- Setting parameters with the `set` command will only change  
    them in your current session, not permanently.  
    

To see all of a node’s current parameter values:

- `ros2 param dump <node_name>`

To load parameter values to a node:

- `ros2 param load <node_name> <parameter_file>`

To start a node with modified parameters instead of default ones:

- `ros2 run <package_name> <executable_name> --ros-args --params-file <file_name>`