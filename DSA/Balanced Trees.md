Prioritize breadth instead of depth
Nodes used in these trees have a height attribute (updated with every insertion, deletion or rotation)

### AVL Trees 
- For every node in the tree, the height of its children can vary by at most 1.
	- Ex: a node with children heights 1 and 5 is not allowed
- Uses rotations to swap around nodes.
- `Balance factor = height of left node - height of right node`
	- Bounded from -1 to 1. 
	- Associated with every node.
	- Calculated every time we insert a new node.

### Left Rotations 
- Done when tree is right heavy
- Parent becomes left child of current right child.

### Right Rotations 
- Done when tree is right heavy
- Parent becomes right child of current left child