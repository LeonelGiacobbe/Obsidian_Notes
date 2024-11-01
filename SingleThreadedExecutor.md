```c++
	rclcpp::executors::SingleThreadedExecutor executor;
	executor.add_node(node);
	executor.spin();
```