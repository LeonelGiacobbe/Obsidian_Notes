Link: https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/

### Keys to solve
- Usual implementation of `slow` and `fast` pointers to find middle of a list, but
	- Also need to have a prev pointer that points to `slow` before `slow = slow.next`
	- Then just skip a node `prev.next = slow.next`

### Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteMiddle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return None
        slow, fast = head, head
        prev = None

        while fast and fast.next:
            prev = slow
            slow = slow.next
            fast = fast.next.next

        # Now slow is middle node, delete it
        prev.next = slow.next

        return head
```