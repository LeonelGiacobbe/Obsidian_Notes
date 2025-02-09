Link: https://leetcode.com/problems/longest-consecutive-sequence/


### Keys to solve:
- make a set of original array
- Iterate to find every `n` which is the beginning of a sequence (`n-1` not in set)
	- Iterate while `n+length` in set
- Take max between `curr` and `prev`, then return the longest

### Code
```python
class Solution:

	def longestConsecutive(self, nums: List[int]) -> int:
	
	
	numSet = set(nums)
	
	longest = 0

	for n in numSet:
	
		if n-1 not in numSet:
	
			length = 0
	
		while n + length in numSet:
		
			length += 1
		
		longest = max(longest, length)

	return longest

```