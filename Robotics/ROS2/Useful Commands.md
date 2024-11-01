---
Status: Not started
Nav2: false
---
- `ros2 service list` returns a list of all active  
    [[Services]] in the system.  
    - Adding the `t` option will also show you the types
- `ros2 topic list` returns a list of all active [[Topics]]  
    in the system.  
    
- `ros2 service find <type_name>` finds all the  
    services of a specific type  
    
- `ros2 interface show <type_name>` shows the  
    structure of the input arguments  
    - arguments above `--` are needed to call [[Services]].  
        Arguments below the line show the structure of the data returned  
        
- `ros2 service call <service_name> <service_type> <arguments>`  
    call [[Services]]  
    
- `ros2 run rqt_graph rqt_graph` allows us to see the graph  
    of our system  
    
- `ros2 param get` To see a parameter’s type.
- `get_logger().info("Some message")` to print “Some  
    message” to the terminal