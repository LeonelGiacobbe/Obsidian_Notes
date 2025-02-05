Link: https://leetcode.com/problems/jump-game/


### Keys to solve:
- Start from the end
- Iterate back and find an index where `nums[i] >= (last - i)`
	- If not found, means we can't jump to that position
- Keep a boolean flag to check for changes in `last`
- Iterate until you get to the first index

### Code
```python
class Solution:

	def canJump(self, nums: List[int]) -> bool:
	
		"""
		
		Start at last index. Find a prev index where
		
		distance is <= max jump. Now treat that as last and
		
		repeat until we get to first index
		
		"""
		
		last = len(nums) - 1
		
		
		
		while last > 0:
		
			iter = last - 1
			
			found = False
			
			while iter >= 0:
			
				if nums[iter] >= (last - iter):
				
					last = iter
					
					found = True
					
					break
			
				iter -= 1
			
			if not found:
			
				return False
		
		return True

```