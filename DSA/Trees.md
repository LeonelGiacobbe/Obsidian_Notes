==RECURSION is extremely helpful when working tree problems==

A tree is similar to [[Linked Lists]], the only difference being that [[Nodes]] in Trees can link to more than one node child. Each node, however, can only have one parent.

A [[C++]] class for a Tree might look like this:
```c++

class Node {
	int data;
	Node* child1;
	Node* child2;
	Node* child3;
	Node(): data(0), left(nullptr), right(nullptr) {}

	int degree() const;
}
 # In the class above, not all nodes have to have three children, they can have less. Set unused notes to a nullptr
```



### Tree Traversal 
- [[Pre-order traversal]]:
	- Visit current node before visiting its children
- [[In-order traversal]]:
	- Visit left child, then current node, then right child
- [[Post-order traversal]]:
	- Visit both children before visiting the current node