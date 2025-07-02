Link: https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/

### Keys to solve
- Use binary search
	- Once number is found, keep checking the sub-array left and right of that number
	- Use a `bool` tag to indicate left or right
	- Set `l = indexFound + 1` in right bias and `r = indexFound - 1` in left bias

### Code
```python
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        low = self.binarySearch(nums, target, True)
        high = self.binarySearch(nums, target, False)

        return [low, high]

    def binarySearch(self, nums, target, leftBias):
        l, r = 0, len(nums) - 1
        index = -1
        while l <= r:
            m = (l + r) // 2
            if target > nums[m]:
                l = m + 1
            elif target < nums[m]:
                r = m - 1
            else: # Num found, keep checking left / right sub-array
                index = m
                if leftBias:
                    r = m - 1
                else:
                    l = m + 1

        return index
```