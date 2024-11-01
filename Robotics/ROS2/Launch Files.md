---
Status: Not started
Nav2: false
---
==**NOTE: AFTER BUILDING A LAUNCH FILE, GO TO THE TOP LEVEL OF THE WORKSPACE AND RUN**== ==`**COLCON BUILD**`====**.**==

  

  

The following is an example of a launch file:

```Python
from launch import LaunchDescription
from launch_ros.actions import Node

def generate_launch_description():
    return LaunchDescription([
        Node(
            package='turtlesim',
            namespace='turtlesim1',
            executable='turtlesim_node',
            name='sim'
        ),
        Node(
            package='turtlesim',
            namespace='turtlesim2',
            executable='turtlesim_node',
            name='sim'
        ),
        Node(
            package='turtlesim',
            executable='mimic',
            name='mimic',
            remappings=[
                ('/input/pose', '/turtlesim1/turtle1/pose'),
                ('/output/cmd_vel', '/turtlesim2/turtle1/cmd_vel'),
            ]
        )
    ])
```

  

### The import statements

- ==_**TODO. CLARIFY WHAT THEY DO**_==

  

### The `generate_launch_description` method:

- This method returns a `LaunchDescription` (which was imported from `launch`)
- Inside the `return` statement, 3 actions are created. They have the following params:
    - `package`: name of the package where the node resides.
    - `namespace`: same concept as namespaces in code. This allows us to name two nodes the same thing while avoiding namespace collisions.
    - `executable`: the name of the node that we want to actually execute. If we are executing `ros2 run turtlesim turtlesim_node`, then the `executable` must equal `turtlesim_node`.
    - `name`: a name assigned to the node, can be whatever we want.

  

# Launching a launch file

- Head to the directory where the file was created
- `ros2 launch <launch_file_name>`
- If the launch file is provided by a package, the syntax is:
    - `ros2 launch <package_name> <launch_file_name>`

  

# Integrating launch files into packages

- Create a `launch` directory inside the `src` folder of your workspace

  

To allow colcon to locate our packages:

- open `setup.py` inside the `src` folder
    - Add the following two lines at the top:
        - `import os`
        - `from glob import glob`
- Under `data_files`, add the following:
    - `(os.path.join('share', package_name, 'launch'), glob(os.path.join('launch', '*launch.[pxy][yma]*')))`