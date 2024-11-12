- Finds a path between two vertices by exploring each possible path as deep as possible before moving to another path
- Builds [[Notes/DSA/Trees|Trees]] from which you can find paths.
- IF a path exists, DFS is guaranteed to find it (but it wont always find the most optimal)

### How it works
- Start at a node
- Select an unvisited node. Make it the current node
- If current node has no unvisited neighbors, go back one step. Find another unvisited node.