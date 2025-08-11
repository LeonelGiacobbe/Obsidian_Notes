Link: https://leetcode.com/problems/climbing-stairs/

### Keys to solve
- Looks complex but it's just Fibonacci sequence
- The number of ways to get from the `nth` step to the end is the sum of the ways of the `nth -1` and `nth - 2` steps.


### Code
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        if n <= 2:
            return n
        prev, cur = 1, 2

        for i in range(2, n):
            # Prev now stores cur, cur is now sum of itself plus prev
            prev, cur = cur, prev + cur

        return cur
```