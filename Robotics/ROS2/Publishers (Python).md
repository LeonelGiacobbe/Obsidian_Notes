---
Status: Not started
Nav2: false
---
To make a publisher in Python:

- Making a publisher means to broadcast the value of a node's variable.
- We import a class that is able to publish data:
    - A good one to use is `from std_msgs.msg import String`
        - It imports a built in `String` message type.
- Inside of our Node (class):
    - `self.variableName = self.create_publisher(type, "name", queue_size)` where type is the type of the [[Topics]] being broadcasted and name is the topics' name (accessible by calling `ros2 topic list`, or you can create your own).
        - `Queue_size` is a buffer. Use 10 by default
        - if `type` is `String`, for example, `create_publisher` declares that this node publishes messages of type `String`

  

## Callback function

```Python
def timer_callback(self):
        msg = String() # Instance object of a class
        msg.data = 'Hello World: %d' % self.i
        self.publisher_.publish(msg)
        self.get_logger().info('Publishing: "%s"' % msg.data)
```

## Sending data to a topic

- Use a class that can communicate through topics. create variables of that class like `msg.var_1`
- `self.variable_name.publish(class)` were `class` is an instance of a class that is able to communicate through a topic (it publishes all variables, such as `msg.var_1` above)
    - if using `String`, the declaration of the `msg` instance object would be `msg = String()`