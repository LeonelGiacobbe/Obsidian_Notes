```
postOrder(node)
	if node == nullptr
		return
	else:
		postOrder(node->left)
		postOrder(node->right)
		print(node->data)
```