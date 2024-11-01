---
Status: Not started
Nav2: false
---
This page leads to:

[[Action Server]]

[[Action Client]]

  

- Method of communication in ROS. Used for long running tasks
- Consist of three parts:
    - Goal
    - Feedback
    - Result
- Actions are built on [[Topics]]and [[Services]].
- Similar to services, but can be cancelled.

Actions use a client-server model. An action client node sends a goal  
to an action server node, and the latter one returns a stream of  
feedback and a result.  

  

Creating action servers and clients does not require them to be inside a [[Workspaces]], though it might be a good idea to keep them in there anyway.

  

If written in python, the way to call an `Action Server` is:

- `python3 name_of_server.py`

  

Actions are defined in `.action` files of the form:

`# Request --- # Result --- # Feedback`

  

# Sending a goal

The syntax to send a goal from the command line is `ros2 action send_goal <action_name> <action_type> <values>`

Overview of parameters:

- `<action_name>` should be the same as the name of the action that was passed as a parameter when creating the `ActionServer` object.
- `<action_type>` should be the path to the type of action we want to use. It seems to be a relative path starting from the directory after the overall workspace where the pkg is stored (so the path should start with the pkg name). **NOT SURE ABOUT THIS, LOOK IT UP.**
- `<values>` refers to what we want to parse through our action to be executed. The format is `"{order:` **`something`**`}"`.