Link: https://leetcode.com/problems/longest-increasing-subsequence/

### Keys to solve
- make a new array `longest` of the same size as `nums` and populate it with ones. The reason for this is we start with the assumption that, if we end the subsequence with the element at `i`, then the length of that subsequence will be at least one (the number itself).
- Iterate over the numbers in `nums`
	- At position `i`, go over all the values between 0 and `i` in `longest`, and keep track of the max if `nums[j] < nums[i]`. Once you're done, `longest[i] += max` 
- Return `max(longest)`

### Code
```python
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        longest = [1] * len(nums)

        for i in range(len(longest)):
            tmp = 0
            for j in range(0, i):
                if nums[j] < nums[i]:
                    tmp = max(tmp, longest[j])

            longest[i] += tmp

        return max(longest)
```