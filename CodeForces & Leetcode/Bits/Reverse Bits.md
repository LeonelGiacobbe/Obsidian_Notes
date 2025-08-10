Link: https://leetcode.com/problems/reverse-bits/

### Keys to solve:
- Start with `res = 0`
- Since we assume 32-bit numbers, iterate 32 times:
	- Bit shift res to the left by 1, extract `LSB` and add it to res, then bit shift the original number to the right by 1

```python
class Solution:
    def reverseBits(self, n: int) -> int:
        res = 0

        for i in range(32): # since we assume 32 bit
            
            res = res << 1 # shift left by 1
            bit = n%2 # extract LSB
            res += bit # add it to res
            n = n >> 1 # right shift by 1 
            # res and n are shifted in reverse

        return res

```