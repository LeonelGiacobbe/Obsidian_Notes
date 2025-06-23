Link: https://leetcode.com/problems/reorder-list/

### Keys to solve:
- Reverse second half and then insert elements from that half into the middle of elements from the first half


### Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reorderList(self, head: Optional[ListNode]) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
        slow = head
        fast = head.next

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        # Reverse second half of the array
        second = slow.next
        prev = slow.next = None
        while second:
            tmp = second.next
            second.next = prev
            prev = second
            second = tmp

        first, second = head, prev

        while second:
            # store vals in temp because we'll be modifying these links
            tmp1, tmp2 = first.next, second.next
            # insert element from second half between head and head.next
            first.next = second
            second.next = tmp1
            first, second = tmp1, tmp2
        

        
```