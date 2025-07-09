Link: https://leetcode.com/problems/serialize-and-deserialize-binary-tree/

### Keys to solve
- To serialize: use `dfs` to iterate over a tree. Append `N`, `None`, or something like that if the node is null. Else, append the `str` version of the value
	- Remember to convert to a string using `",".join(list)`
- To deserialize: split the data using `data.split(",")` into a list
	- Start a counter at 0 and initialize a `TreeNode`
	- If the value at the current counter in the list represents null, increment counter and return None. Else, make a new node with the value at the current counter in the list, and call dfs into `node.left` and `node.right`

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Codec:

    def serialize(self, root):
        """Encodes a tree to a single string.
        
        :type root: TreeNode
        :rtype: str
        """
        res = []
        def dfs(node):
            if not node:
                res.append("N")
                return
            res.append(str(node.val))
            dfs(node.left)
            dfs(node.right)
            return 
        dfs(root)
        return ",".join(res)     

    def deserialize(self, data):
        """Decodes your encoded data to tree.
        
        :type data: str
        :rtype: TreeNode
        """
        values = data.split(",")
        self.i = 0
        tree = TreeNode()
        
        def dfs():
            if values[self.i] ==  "N":
                self.i += 1
                return None
            
            node = TreeNode(int(values[self.i]))
            self.i += 1
            node.left = dfs()
            node.right = dfs()

            return node
        return dfs()
```