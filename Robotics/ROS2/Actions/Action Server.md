# Building an action

Example code of what an action server may look like:

```Python
import time


import rclpy
from rclpy.action import ActionServer
from rclpy.node import Node

from action_tutorials_interfaces.action import Fibonacci


class FibonacciActionServer(Node):

    def __init__(self):
        super().__init__('fibonacci_action_server')
        self._action_server = ActionServer(
            self,
            Fibonacci,
            'fibonacci',
            self.execute_callback)

    def execute_callback(self, goal_handle):
        self.get_logger().info('Executing goal...')


        feedback_msg = Fibonacci.Feedback()

        feedback_msg.partial_sequence = [0, 1]


        for i in range(1, goal_handle.request.order):

            feedback_msg.partial_sequence.append(

                feedback_msg.partial_sequence[i] + feedback_msg.partial_sequence[i-1])

            self.get_logger().info('Feedback: {0}'.format(feedback_msg.partial_sequence))

            goal_handle.publish_feedback(feedback_msg)

            time.sleep(1)


        goal_handle.succeed()

        result = Fibonacci.Result()

        result.sequence = feedback_msg.partial_sequence

        return result


def main(args=None):
    rclpy.init(args=args)

    fibonacci_action_server = FibonacciActionServer()

    rclpy.spin(fibonacci_action_server)


if __name__ == '__main__':
    main()
```

  

- It’s important to import the `ActionServer` from `rclpy.action`
    - An ActionServer requires four parameters: `node`, `action_type`, `action_name`, and `execute_callback`; in that order.
        - Most of the time, `node` will be self.
        - `action_type` will be the action type of action we want to execute, in this case imported from `something.action` at the top (in this case, `Fibonacci`).
        - `action_name` is a string, most of the time will be the same as `action_type`
        - `execute_callback` is a function that gets called every time the `ActionServer` is executed.

### Overview of `execute_callback` function:

- `self` and `goal_handle` are the parameters. `self` is obvious, should always be included when building methods inside classes.
- `feedback_msg = Fibonacci.Feedback()` assigns the feedback part of the action to `feedback_msg`.
- `goal_handle.request.order` refers to the value that was passed as a request by the action client.
- `goal_handle` refers to the state of the goal after executing the callback. If the user does not manually declare the state of the handle, `aborted` is assumed by default. Will normally want to do `goal_handle.succeed()`, since, if the callback is called, the execution of the actions is assumed to be successful.
- `self.get_logger().info()` prints to the screen whatever parameter was passed through the second set of parentheses.
- By doing `result = Fibonacci.Result()` we are extracting the result part of the `.action` file that was imported at the top of the file. Remember that `.action` files have 3 parts, Request, Result, and Feedback.
- We then return `result`, which is the info contained in the `.action` file.
- _Explanation for the whole feedback part is in its own subsection below_

### The `main` function:

- Straightforward excecution of the `main` function like in any other `ROS2` class.
- defining `main` with `args=None` as parameters
- calling `rclpy.init(args=args)`
- creating an instance object of the class.
- calling `rclpy.sping(object_name)` to keep the node alive until the user manually kills it.

### Publishing feedback

- We can make our action server publish feedback for action clients by calling the goal handle’s [publish_feedback()](http://docs.ros2.org/latest/api/rclpy/api/actions.html#rclpy.action.server.ServerGoalHandle.publish_feedback) method.
- we can create an object and assign it with `<action_type>.Feedback()`. With feedback we can return partial status messages to the command line without waiting for the program to be complete.
- We can add fields to the `Feedback()` object. Above, the field `partial_sequence` is added.
- `goal_handle.publish_feedback` prints the feedback to the terminal where the action is being executed. This differs from the `get_logger().info` line, since that prints the information to the terminal where the action is called. `publish_feedback` can be used to debug or for progress messages that we don’t want to print to the client.