---
Status: Not started
Nav2: false
---
make sure to import the message type that we want to listen to with all the other import statements at the beginning, like so:

- if msg type is `/turtlesim/msg/Pose`, do `from turtlesim.msg import Pose`
    - dont forget to add dependency if package is not already added in the dependencies list.

  

Just as when creating [[Publishers (Python)]], to create a subscriber, we create an object inside of our `init` function inside of our Node class (see [[Nodes (Python)]]):

- `self.some_subscriber= self.create_subscription(Type, topic, callback, queue_sz)`
- Above, we created an object called `'some_subscriber'`. We specify the type to know the format of what we will be listening to. we specify the [[Topics]]to know where to listen, and the callback is something that gets executed every time we receive info (like printing something to the terminal.)
- The callback is usually a function that only takes one parameter (besides `self`). That is the message to be received. should be done like so:
    - `def subscriber_callback(self, type)` where type is the message type.
        - if we want to print the msg to terminal: `self.get_logger().info(str(msg))`

  

## How to install a node in Python

- Go to `setup.py` inside your `src` directory
- Inside `entry points` -> `console scripts` add the following line:
    - `"some_name = package_name.file_name:function_to_run"`
- Go to your workspace directory and run `colcon build --symlink-install` to build a package (only needs to be done one time for every file. Still needs to be done after creating a new file)
- After every change we make in the code:
    - run `source ~/.bashrc` in the same directory as above

After that, you can run a node with `ros2 run package_name name_in_setup.py`