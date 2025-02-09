Link: https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii

### Keys to solve:
- Not intuitive. Swaps need to be made when `count <= 2`
- Does one swap per `i` pass, making it `O(n) and not O(n^2)`

### Code
```python
class Solution:

	def removeDuplicates(self, nums: List[int]) -> int:
	
	j = 1
	
	n = len(nums)
	
	count = 1
	
	for i in range(1, n):
	
		if nums[i] == nums[i-1]:
		
			count += 1
	
		else:
	
			count = 1
	
		if count <= 2:
	
			nums[j] = nums[i]
	
			j += 1
	
	return j

```