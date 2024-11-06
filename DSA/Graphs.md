Use nodes, like [[Trees]]

### Directed vs Undirected
- In directed graphs, connections between nodes are unilateral.
	- In undirected, they are not (always back and forth).


### Adjacency Matrix
-  2D array 
- Pair of indices that indicate whether an edge is in the graph `(1)` or not `(0)`
	- If there is an edge from `A` to `B`, then entry `[A][B] = 1`
	- Instead of one and zero, it could store the weight of the edge, with a known value signifying the edge does not exist.

### Adjacency List
- 
### Terminology 
- `In-degree`: amount of edges coming into a node
- `Out-degree`: amount of edges coming out of a node
	- In undirected graphs, `in` and `out` degree are the same.
- if `(a,b)` is an edge in a graph, `a` is said to be adjacent to `b`, and vice versa.
- `Incident`: edge that goes into a node
- `Connected tree`: a tree where you can get to every node from any node