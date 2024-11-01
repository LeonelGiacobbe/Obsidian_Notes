---
Status: Not started
Nav2: false
---
To create [[Nodes]] in Python:

- go to `src/project_name/project_name` and create a file with a`.py` extension
- give the file permissions to be executable
- Add interpreter line `#!/usr/bin/env python3.`
    - import `rclpy`
    - add `from rclpy import Node`.
- Create a `main` function with its parameters. By default -> `def main(args=None)`
    - first line in `main` function: `rclpy.init(args=args)` to initialize ROS communication
    - last line in `main` function: `rclpy.shutdown()` to cease ROS communication
- Create a class that inherits from Node -> `class myNode(Node):`
- Each node we create is going to be a class object that inherits from the `rclpy` node (hence the import statement).
    - Inside the class, create a constructor ('_ _ init _ _ _') :
        - Inside the constructor, call the constructor of the super class (`Node` from `rclpy`) -> `super().__init__("Node Name in here")`
- Inside the `main` function, create an instance of the node with its parameters (if any).
- If you want to keep a node alive until a user manually kills it, call `rclpy.spin('name of node object')` inside the `main` function.
- If you want to run the Node from the terminal, add this in the end: `if __name__ == "__main__:` and call `main()` inside the if clause  
      
    

### How to install a node in Python

- Go to `setup.py` inside your `src`  
    directory  
    
- Inside `entry points` -> `console script` add the following line:
    - `"some_name = package_name.file_name:function_to_run"`
- Go to your workspace directory and run `colcon build --symlink-install` to build a package (only needs to be done one time for every file. Still needs to be done after creating a new file)
- After every change we make in the code:
    - run `source ~/.bashrc` in the same directory as above
- After that, you can run a node with `ros2 run `package_name` name_in_setup.py

### Package Dependencies

Any package that we use besides `rclpy` needs to be added under the `<depend>` section in the  
  
`package.xml` file within our workspace:

-`<depend> packageName </depend>`