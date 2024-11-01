---
Status: Not started
Nav2: false
---
To run navigation nodes:

- run `roscore` if it is not already running.
- run `roslaunch turtlebot3_bringup turtlebot3_robot.launch`
- run `roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:={path to map}` . Make sure the path is to the `.yaml` file.

# Estimating initial pose