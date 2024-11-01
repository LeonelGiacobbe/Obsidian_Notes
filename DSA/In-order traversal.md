```
inOrder(node)
	if node == nullptr
		return
	else:
		inOrder(node->left)
		print(node->data)
		inOrder(node->right)

``` 