---
Status: Not started
Nav2: true
---
> [!important]  
> A ‘Node’ when discussing behavior trees is NOT the same as a [[Nodes]] in [[ROS2]]  

  

## ==Action Nodes==

==See== ==[[Actions]]== ==for more info==

- `ComputePathToPose` - `ComputePathToPose` Action Server Client (Planner Interface)
- `FollowPath` - `FollowPath` Action Server Client (Controller Interface)
- Spin, Wait, Backup - Behaviors Action Server Client
- `ClearCostmapService` - `ClearCostmapService` Server Clients

Upon completion, these action nodes will return `SUCCESS` if the action server believes the action has been completed correctly, `RUNNING` when still running, and will return `FAILURE` otherwise.

  

## ==Condition nodes==

- `GoalUpdated` - Checks if the goal on the goal topic has been updated
- `GoalReached` - Checks if the goal has been reached
- `InitialPoseReceived` - Checks to see if a pose on the `intial_pose` topic has been received
- `isBatteryLow` - Checks to see if the battery is low by listening on the battery topic

These condition nodes are mainly used to probe the system they’re running on and ensure it’s working properly. They will typically return `SUCCESS` if the condition is true and `FAILURE` otherwise

  

## ==**Control: PipelineSequence**==

This node checks the status of all the children of a specific node. If a children goes from returns `SUCCESS`, then that node gets ticked off and the next node at the same level goes from `IDLE` to `RUNNING`

  

## ==Control: Recovery==

This node has two children nodes and returns `SUCCESS` if and only if the first child returns `SUCCESS`. If the first child returns `FAILURE`, the second child will be ticked. This loop will continue until either:

- The first child returns `SUCCESS` (which results in `SUCCESS` of the parent node)
- The second child returns `FAILURE` (which results in `FAILURE` of the parent node)
- The `number_of_retries` input parameter is violated

This node is usually used to check that an action was completed successfully. There’s a ‘main’ action, and if that action returned `FAILURE`, then the recovery node gets ticked.

  

## ==Control: Roundrobin==

Ticks children in a round-robin fashion until one returns `SUCCESS`, in which case the parent will do the same. If one of the children returns `FAILURE`, then the control node will do the same.