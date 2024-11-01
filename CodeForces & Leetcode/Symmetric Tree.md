Link: https://leetcode.com/problems/symmetric-tree/
Language: Python
Topics: [[C++/Recursion|Recursion]]
Keys to solve: 
- Symmetry is checked through the middle of the tree (see code for better explanation)
- Chaining checking with `and` is not dangerous since once one evaluates to `False` , the function will return `False`

### Optimal Code 
```Python 
class Solution:

    def isSymmetric(self, root: Optional[TreeNode]) -> bool:        

        def dfs(left, right):

                if not left and not right:

                    return True

                if not left or not right:

                    return False

  

                return (left.val == right.val and

                dfs(left.left, right.right) and

                dfs(left.right, right.left))

  

        return dfs(root.left, root.right)
```