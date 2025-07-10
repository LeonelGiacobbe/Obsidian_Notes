Link: https://leetcode.com/problems/maximum-subarray/

### Tips to solve:
- Use `Kadane's Algorithm`
- Keep a current and overall sum
	- If at any point the current sum is less than zero, set the sum to zero
		- This is because the previous added numbers yielded a negative sum, and we can just disregard that sum and start fresh with a value of zero

### Code
```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        """
        Two pointers? if positive, expand to include it. If not, choose
        the lesser negative
        check with sum() and store index if max is modified
        """
        max_sum = float('-inf') # minimum possible val
        curr_sum = 0

        for i in range(len(nums)):
            # Add current num to tmp sum
            curr_sum += nums[i]
            # Take max between aggregate and current
            max_sum = max(max_sum, curr_sum)
            # If current sum is negative, then we can disregard the 
            # numbers we've added before and start fresh, since 0 > neg number
            if curr_sum < 0:
                curr_sum = 0

        return max_sum
```