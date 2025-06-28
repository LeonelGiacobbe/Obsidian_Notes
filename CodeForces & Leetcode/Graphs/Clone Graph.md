Link: https://leetcode.com/problems/clone-graph/


### Keys to solve: 
- Use DFS and a hash map
	- Hash map is used to avoid cloning the same node twice
- For every node, make a copy of it (if not already done). Map original to copy in hash map. 
- Iterate over the og node's neighbors and append dfs(neighbor) to the list of the copy's neighbors

### Optimal Code:
```python
from typing import Optional
class Solution:
    def cloneGraph(self, node: Optional['Node']) -> Optional['Node']:
        # Create a hash map to not create repeated nodes
        oldToNew = {}

        def dfs(node):
            # If node has already been copied, return it
            # (Base case)
            if node in oldToNew:
                return oldToNew[node]
            
            # Else, clone it
            copy = Node(node.val)
            # Make a mapping from old to new
            oldToNew[node] = copy
            # Add its neighbors
            for nei in node.neighbors:
                copy.neighbors.append(dfs(nei))

            # Now node has been deep copied
            return copy
        
        return dfs(node) if node else None
```
### Image for visualization
![[Pasted image 20250621121517.png]]