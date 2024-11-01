The code for a simple example client may look like this:

```Python
import rclpy
from rclpy.action import ActionClient
from rclpy.node import Node

from action_tutorials_interfaces.action import Fibonacci


class FibonacciActionClient(Node):

    def __init__(self):
        super().__init__('fibonacci_action_client')
        self._action_client = ActionClient(self, Fibonacci, 'fibonacci')

    def send_goal(self, order):
        goal_msg = Fibonacci.Goal()
        goal_msg.order = order

        self._action_client.wait_for_server()

        self._send_goal_future = self._action_client.send_goal_async(goal_msg, feedback_callback=self.feedback_callback)

        self._send_goal_future.add_done_callback(self.goal_response_callback)

    def goal_response_callback(self, future):
        goal_handle = future.result()
        if not goal_handle.accepted:
            self.get_logger().info('Goal rejected :(')
            return

        self.get_logger().info('Goal accepted :)')

        self._get_result_future = goal_handle.get_result_async()
        self._get_result_future.add_done_callback(self.get_result_callback)

    def get_result_callback(self, future):
        result = future.result().result
        self.get_logger().info('Result: {0}'.format(result.sequence))
        rclpy.shutdown()

    def feedback_callback(self, feedback_msg):
        feedback = feedback_msg.feedback
        self.get_logger().info('Received feedback: {0}'.format(feedback.partial_sequence))


def main(args=None):
    rclpy.init(args=args)

    action_client = FibonacciActionClient()

    action_client.send_goal(10)

    rclpy.spin(action_client)


if __name__ == '__main__':
    main()
```

### The import statements

- Make sure to import `ActionClient` from `rclpy.action`.
- `from action_tutorials_interfaces.action import Fibonacci` allows us to use the action type Fibonacci (see [[Actions]]).

  

### The ‘__init__’ method:

- As with all `__init__`functions, it calls the `__init__` of the super class.
- Then we also create an instance object of the `ActionClient` class. An `ActionClient` requires three parameters: `node`, `action_type`, and `action_name`; in that order.
- Most of the time, `node` will be self.
- `action_type` will be the action type of action we want to execute, in this case imported from `something.action` at the top (in this case, `Fibonacci`).
- `action_name` is a string, most of the time will be the same as `action_type`

  

### The `send_goal` method:

- `goal_msg = Fibonacci.Goal()` assigns the goal part of the action format to `goal_msg`
- `self._action_client.wait_for_server()` waits for the Action Server to be available. Then it sends a goal to the server.
- `self._action_client.send_goal_async(goal_msg)` returns a future to a goal handle. This future is basically a ‘task’ that gets completed whenever the Action Server accepts or rejects the goal request. Look at `goal_response_callback` section below for more info.
- `self._send_goal_future.add_done_callback(self.goal_response_callback)` calls the `goal_response_callback` method below, which returns the status of the communication.
- Look at `goal_response_callback` section below for more info.
- ==_**TODO: ADD DESCRIPTIONS FOR WHAT THE REST OF THE METHOD DOES.**_==

  

### The `goal_response_callback` method:

- It takes `self, future` as parameters
- `goal_handle = future.result()` allows us to use this variable to check if the result of the communication was successful or not.
- The if statement below it tells the user if the communication failed.
- We create a result future that becomes ‘idle’ until the server is done communicating with the client.
- We can also use the goal handle to request information. This is done with `goal_handle.get_result_async()`. This will trigger the goal handle
- We also register a callback to log what the program is doing to the terminal.

  

### The `get_result_callback` method:

- `result = future.result().result` gets the result from the communication, and prints the result to the terminal.
- It is also in charge of shutting down `rclpy`

  

### The `feedback_callback` method:

- `feedback_msg` is a way for us to get the feedback portion of the Action message (look at [[Actions]] for the complete Action format).