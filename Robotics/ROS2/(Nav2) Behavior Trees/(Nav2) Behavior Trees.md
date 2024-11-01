---
Status: Not started
Nav2: true
---
# ==Navigation sub-tree==

Graphic View of the sub-tree:

![[Screenshot_from_2024-02-12_08-08-12.png]]

XML file of the sub-tree:

```XML
<PipelineSequence name="NavigateWithReplanning">
    <RateController hz="1.0">
        <RecoveryNode number_of_retries="1" name="ComputePathToPose">
            <ComputePathToPose goal="{goal}" path="{path}" planner_id="GridBased"/>
            <ReactiveFallback name="ComputePathToPoseRecoveryFallback">
                <GoalUpdated/>
                <ClearEntireCostmap name="ClearGlobalCostmap-Context" service_name="global_costmap/clear_entirely_global_costmap"/>
            </ReactiveFallback>
        </RecoveryNode>
    </RateController>
    <RecoveryNode number_of_retries="1" name="FollowPath">
        <FollowPath path="{path}" controller_id="FollowPath"/>
        <ReactiveFallback name="FollowPathRecoveryFallback">
            <GoalUpdated/>
            <ClearEntireCostmap name="ClearLocalCostmap-Context" service_name="local_costmap/clear_entirely_local_costmap"/>
        </ReactiveFallback>
    </RecoveryNode>
</PipelineSequence>
```

  

### Execution of the sub-tree:

It has two primary actions:

- `ComputePathToPose`, both children of `PipelineSequence`:
- `FollowPath`

`ComputePathToPose` gets ticked, then `FollowPath` is ticked. While `FollowPath` is in the process of being ticked, the `ComputePathToPose` sub-tree gets ticked again, allowing the robot to recalculate its path while it is executing it.

  

### Recovery sub-tree