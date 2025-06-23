Link: https://leetcode.com/problems/product-of-array-except-self/

### Keys to solve:
- Build two subarrays, left and right
	- At each index of those arrays, the element is the product of all elements left and right of that position in the original array
- By using iterators i and j, we only need to pass once. i is regular increasing, `j = -i - 1`, so they start at the end points and move opposite each other
### Solution
```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
	    # temp values to store in left and right
        l_mult = 1
        r_mult = 1
        n = len(nums)
        left = [0] * n
        right = [0] * n
        

        for i in range(n):
            j = -i - 1 # iterates over nums backwards
            left[i] = l_mult
            right[j] = r_mult
            l_mult *= nums[i]
            r_mult *= nums[j]

        return [l * r for l, r in zip(left, right)]

```