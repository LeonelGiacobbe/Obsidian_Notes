BSTs are a special kind of [[DSA/Trees|Trees]] where each node has at most two children. The left children (and its descendants) will have a value $\leq$ the parent and the right children (and its descendants) will have a value $\geq$ the parent.
### Example BST:
![[Pasted image 20240922185605.png]]

### Implementation
- Usually implemented with [[Linked Lists]], where each node contains 3 fields
	- data 
	- left child 
	- right child
### BST Methods
- Search pseudocode:
```
bool search(node, x):
	if node == nullptr return false
	if x  < node->val search(node->left)
	if x  > node->val search(node->right)
	return true
```
- Insert pseudocode:
```
insert(node, x):
if node == nullptr 
	New Node(x) 
	return true
if x > node->val 
	return insert(node->right, x)
if x < node->val 
	return insert(node->left, x)
return false
```
- delete (pseudocode)
```
delete(root, x)
if x > node->val 
	delete(node->right, 65)
if x < node->val 
	delete(node->left, 65)
if node == x
	if degree == 0: // no children
		delete node 
		node == nullptr 
	if degree == 1: // 1 child
		if node->left != nullptr:
			node = node->left
		else:
			node = node->right
		delete node
	if degree == 2: // 2 children. Take largest val of left subtre 
		tmp = node->left
		loop while tmp->right != nullptr
			tmp = tmp->right
		 node->value = tmp->value
		 delete(node->left, tmp->data)
		
```