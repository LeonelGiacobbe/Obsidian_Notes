


### Steps 
1) Initialize an `action` object from the `Base_pb2` class. give it a `.name` and `.application_data` if needed.
2) `feedback = base_cyclic.RefreshFeedback()`. This object is used for receiving updates on robot commands at 1Khz, and is also used to set pose and angular values. 
3) Set `action` type. In cartesian actions, that will most likely be `target_pose` ->`action_obj.reach_pose.target_pose`. 
	1) `target_pose` has `pose_xyz` and `pose_theta_xyz` values. 
4) After filling out all of the required fields for our `action` object, the `base` object simply calls the `executeAction(action)` command.