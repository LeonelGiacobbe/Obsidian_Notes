Link: https://leetcode.com/problems/invert-binary-tree/
Language: Python
Topics: [[C++/Recursion|Recursion]]
Keys to solve: 
- Swap of values using a temporary variable
- _DONT FORGET_ base case for recursion 
- Technically executing [[Pre-Order Traversal]]


### Optimal Solution: 
```Python
class Solution:

    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:

        if(root == None):

            return

        else:

            tmp = root.left

            root.left = root.right

            root.right = tmp

            root.left, root.right = root.right, root.left

            self.invertTree(root.left)

            self.invertTree(root.right)

  

        return root
```