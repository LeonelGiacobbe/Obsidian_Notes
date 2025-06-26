Link: https://leetcode.com/problems/merge-k-sorted-lists/

### Keys to solve
- Sort lists by pairs, store sorted pairs in new list, and repeat
	- While `len(sortedList) >= 1`
- Remember to account for cases where `k` is odd by checking against `len(lists)`


### Code
```python
class Solution:
    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
        if not lists or len(lists) == 0:
            return None

        while len(lists) > 1:
            mergedList = []
            for i in range(0, len(lists), 2):
                l1 = lists[i]
                l2 = lists[i + 1] if (i + 1) < len(lists) else None
                mergedList.append(self.mergeLists(l1, l2))
            lists = mergedList

        return lists[0]
    
    def mergeLists(self, list1, list2):
        dummy = ListNode()
        tmp = dummy

        while list1 and list2:
            if list1.val < list2.val:
                tmp.next = list1
                list1 = list1.next
            else:
                tmp.next = list2
                list2 = list2.next
            tmp = tmp.next

        if list1:
            tmp.next = list1
        if list2:
            tmp.next = list2

        return dummy.next
```