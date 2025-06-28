Link: https://leetcode.com/problems/search-in-rotated-sorted-array/

** NOTE ** : this problem contains [[Find Min in rotated sorted array]]

### Keys to solve
- Find minimum in the array
- After that, check target against first, last and element at min index to set `l` and `r` pointers, then perform regular binary search.

### Code
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l < r:
            m = (l + r) // 2

            if nums[m] > nums[r]:
                l = m + 1
            else:
                r = m

        min_index = l

        if min_index == 0:
            l, r = 0, len(nums) - 1
        elif target >= nums[0] and target <= nums[min_index - 1]:
            l, r = 0, min_index - 1
        else:
            l, r = min_index, len(nums) - 1

        while l <= r:
            m = (l + r) // 2

            if nums[m] == target:
                return m
            if target > nums[m]:
                l = m + 1
            else:
                r = m - 1

        return -1
```