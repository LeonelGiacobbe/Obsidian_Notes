Link: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

### Keys to solve:
- walk through [[Linked Lists]] and append values to array
- Use fast and slow pointer (i and i-1) to iterate `len(values) - n` times
- omit fast pointer (nth node)
- Watch out for edge case when head needs to be removed

### Code
```python
	class Solution:

		def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
		
		tmp = head
		
		vals = []
		
		if head.next is None:
		
			return None
		
		while tmp:
		
			vals.append(tmp.val)
			
			tmp = tmp.next	  
		
		# Special case: removing the head
		
		if n == len(vals):
		
			return head.next
		
		fast = head
		
		slow = None
		
		for i in range(len(vals) - n):
		
			slow = fast
			
			fast = fast.next
		
		if fast and slow:
		
			slow.next = fast.next
			
		return head

```