Link: https://leetcode.com/problems/find-a-corresponding-node-of-a-binary-tree-in-a-clone-of-that-tree/

### Keys to solve:
- Use two pointers `l` and `r`
- Initialize size to `len(nums) + 1`, then check if it's still that value to return zero.
- Increment `r` to the right while keeping a sum, while `sum <= target`
	- Once this condition is broken, increment `l` while `sum >= target`, removing `nums[l]`
- At every point where `sum >= target`, take the minimum between the current minimum and `r - l`

### Solution

```c++
class Solution:

	def minSubArrayLen(self, target: int, nums: List[int]) -> int:
	
		l, r = 0, 0
		
		length = len(nums) + 1
		
		curr_sum = 0
		
		while r < len(nums):
		
			curr_sum += nums[r]
			
			r += 1
			
			while curr_sum >= target:
			
				length = min(length, r - l)
				
				curr_sum -= nums[l]
				
				l += 1
		
		if length == len(nums) + 1:
		
		length = 0
		
		return length
};
```