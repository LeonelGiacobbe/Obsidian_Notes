---
Status: Not started
Nav2: false
---
[[Nodes]]are written inside packages.

ROS packages are organized as follows:

- launch folder: Contains launch files
- `src` folder: Contains the source code (C++, Python)
- CMakeLists.txt: List of [cmake](https://en.wikipedia.org/wiki/CMake) rules for compilation
- `package.xml`: Package information and dependencies

  

## To create a package

- go to `/src` inside our [[Workspaces]]directory
- call `ros2 pkg create 'package name' --build-type ament_'langauge' -- dependencies'something'`
    - `ament` is the name of the build system.
    - `ament_cmake` to develop a package in C++
    - `ament_python --dependencies rclpy` to develop a package in Python.

  

You can create a package dependency list.

`package.xml` is a file contained in every package. It contains:

- The package’s name
- package’s version
- package’s description and maintainer
- package’s dependencies
- package’s build type