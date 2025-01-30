Link: https://leetcode.com/problems/path-sum/

### Keys to solve:
- [[Discrete Structures/Recursion|Recursion]]
- As much as it may look like you should, you shouldn't subtract from the path sum at any point. Counter-intuitive but don't do it
- `return(func(left) or func(right))` makes it so if at any point the sum check is `True`, then that sweeps through the whole recursive call and it will end up returning `True`.

### Code
```python

class Solution:

	def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:

		def traverse(sum, node):

		if not node:
		
			return False 
		
		sum += node.val
		
		if not node.left and not node.right:
		
			return sum == targetSum
		
		return (traverse(sum, node.left) or traverse(sum, node.right))

	sum = 0
	
	return traverse(sum, root)

```