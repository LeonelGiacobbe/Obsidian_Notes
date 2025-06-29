Link: https://leetcode.com/problems/maximum-depth-of-binary-tree/

### Keys to solve:
- At a certain node, its depth is equal to the maximum of the depths between its left and right children.
- in `dfs`, `max_depth = max(depth_left, depth_right, depth)`, we include `depth` itself because, if that node has no or one children, then the respective depths will be zero, so we want to keep the current depth at that point

### Code
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        

        def dfs(node, depth):
            if not node:
                return 0

            depth_left = dfs(node.left, depth + 1)
            depth_right = dfs(node.right, depth + 1)

            max_depth = max(depth_left, depth_right, depth)

            return max_depth

        return dfs(root, 1) if root else 0
```