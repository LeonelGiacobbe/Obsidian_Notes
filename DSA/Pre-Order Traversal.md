Visit the parent first, then the children

```
preOrder(node)
	if node == nullptr
		return
	else:
		print(node->data)
		preOrder(node->left)
		preOrder(node->right)

```