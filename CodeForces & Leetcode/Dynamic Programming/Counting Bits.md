Link: https://leetcode.com/problems/counting-bits/


### Keys to solve
- Populate an array of zeroes of size `n`
- iterate between `1, n + 1`. The amount of ones at `i` will be one more than the amount of ones at `i - offset`
	- Offset starts at 1, and whenever the current iteration number is twice as big as offset, offset becomes that value. This is because the ones and zeros patterns repeat in binary (except for the most significant bit). That most significant bit offset becomes twice as big for every bit added.

### Code
```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        # Populate arr with 0
        arr = [0] * (n + 1)
        # The amount of ones in binary(n) equals 1 = amount of ones in binary(n - MSB)
        offset = 1
        # We start with offset = 1, and once i is double the offset, we reached a power of 2, 
        # We need to set offset to i since that i represents the MSB at that point
        for i in range(1, n + 1):
            if 2 * offset == i:
                offset = i

            arr[i] = 1 + arr[i - offset]

        return arr
```