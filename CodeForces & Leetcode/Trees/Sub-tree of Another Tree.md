Link: https://leetcode.com/problems/subtree-of-another-tree/

### Keys to solve:
- Have one recursive function for equality check (both nodes existing or not, having same value or not)
- Have another function that calls the first one. If the result of the first one is false, traverse the tree and call in child nodes. Do this until result is true or tree is empty

### Code
```python
class Solution:
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        # Basic equality check with recursion
        def sameTree(p, q):
            if not p and not q:
                return True
            if (p and not q) or (q and not p):
                return False
            if p.val != q.val:
                return False

            return sameTree(p.left, q.left) and sameTree(p.right, q.right)

        # Starts with regular root, and checks
        # subtrees of root to match with subRoot
        def has_subtree(tempRoot):
            if not tempRoot:
                return False

            if sameTree(tempRoot, subRoot):
                return True

            return has_subtree(tempRoot.left) or has_subtree(tempRoot.right)

        return has_subtree(root)
```