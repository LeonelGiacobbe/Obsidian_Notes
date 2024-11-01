In [[ROS2]], executors handle the execution of files by utilizing one or more threads in the operating system ROS is running on. 

### ==Basic use== 
When calling `spin()` on a node, we are invoking the [[SingleThreadedExecutor]]:
There's also two more kinds of executors: 
- [[MultiThreadedExecutor]]:
- [[StaticSingleThreadedExecutor]]:

To declare an executor:
`rclcpp::executors::ExecutorType executor;`
and then 
`executor.add_node(nodeName)` to add another node to the executor and manage multiple at the same time.



### ==For Extra Fine-Tuning:==
The explicit Executor class (in `executor.hpp` in `rclcpp`, in `executors.py` in `rclpy`, or in `executor.h` in `rclc`) provides more control over execution management