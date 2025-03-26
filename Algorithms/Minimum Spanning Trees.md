- Tree where all nodes are connected and the summed weight that connects them is minimized.

### Kruskal's MST 
- Picks lowest edge weight that doesn't make a cycle and adds to tree.
	- Loops until MST is achieved
- Edges don't need to be connected when they're added.
- Implemented using a priority queue

### Prim's MST 
- Starts at a defined node
- Picks the lowest vertex that connects to our current tree and does not make a cycle
	- Anywhere, does not need to be at the last node added
