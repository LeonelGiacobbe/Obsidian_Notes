Nodes are individual entities that perform specific tasks within a workspace (see  [[Workspaces]]). They are the building blocks of any system that uses ROS2, and they can communicate with other nodes.  

Nodes are built _inside_ `.py` or `.cpp` files. You can actually create multiple nodes in the same file.  

Nodes communicate with each other by publishing and subscribing to [[Topics]].

We can see the relationships between nodes by looking at the ROS RQT graph.  

Nodes sometimes take [[Parameters]]. These parameters provide a way to configure the behavior of a node.


### Node declaration in [[C++]]
```c++
int main(int argc, char * argv[])

{
  // Initialize ROS and create the Node

  rclcpp::init(argc, argv);

  auto const node = std::make_shared<rclcpp::Node>(
    "NodeName",
    rclcpp::NodeOptions().automatically_declare_parameters_from_overrides(true)

  );
}
```