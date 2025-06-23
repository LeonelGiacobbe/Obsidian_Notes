Link: https://leetcode.com/problems/missing-number/
### Keys to solve:
- Array will contain every element `[0, len(array)]` except for a random number in that range.
- We can use only one loop that, at every iteration, adds index `i` and subtracts the `ith` element of the array. Every `i` except for one will be in the array. Those `i's` will eventually cancel out `+i, -i(from array)`, leaving us with the missing number
	- We initialize `res` to `len(nums)` because loops do not include the last elements, so we account for that
### Code
```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        res = len(nums)

        for i in range(len(nums)):
            res += (i - nums[i])

        return res
```