Link: https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/

### Keys to solve
- Use binary search with slightly different logic
	- Having pointers `l`, `m` and `r`, if `nums[m] > nums[r]`, that means the start of the list (smallest number) is somewhere between index `m` and `r`, because since `nums[m] > nums[r]`, we know there's a point between `m` and `r` where the original list would start, and that is the minimum

### Solution
```python
class Solution:
    def findMin(self, nums: List[int]) -> int:
        l, r = 0, len(nums) - 1

        while l < r:
            m = (l + r) // 2

            if nums[m] > nums[r]:
                l = m + 1
            else:
                r = m
        
        return nums[r]
```