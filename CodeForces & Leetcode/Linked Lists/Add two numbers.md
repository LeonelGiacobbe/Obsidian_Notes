Link: https://leetcode.com/problems/add-two-numbers/


### Keys to solve
- Iterate over both lists and add elements to an overarching sum, multiplying by 10 each time
- make a new linked list, and while the sum above `> 0`
	- append `sum % 10` to the list
	- use integer division to divide by ten and disregard the digit you appended
		- Example: `807. append 7, 807 //= 10 == 80`. `80. append 0, 80 //= 10 == 8`


### Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        num1 = 0
        num2 = 0

        mult = 1
        while l1:
            num1 += (l1.val * mult)
            mult *= 10
            l1 = l1.next
        
        mult = 1
        while l2:
            num2 += (l2.val * mult)
            mult *= 10
            l2 = l2.next

        res = num1 + num2

        if res == 0:
            return ListNode(0)

        dummy = ListNode()
        tmp = dummy

        while res > 0:
            digit = res % 10
            tmp.next = ListNode(digit)
            tmp = tmp.next
            res //= 10

        return dummy.next

```