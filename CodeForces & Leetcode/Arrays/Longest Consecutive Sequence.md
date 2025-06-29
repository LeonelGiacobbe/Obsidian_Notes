Link: https://leetcode.com/problems/longest-consecutive-sequence/

### Keys to solve
- `nums` could have duplicates, but they're useless, so create a set
- iterate for every `num` until `n-1` is not in the set. When that is true, you've found the beginning of a sequence
	- set length to 1, and while `num + length` is in the set, increment length by 1
- Have a var `longest` to store the longest sequence seen yet

### Code
```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0

        for num in numSet:
            if num-1 not in numSet:
                length = 1
                while num + length in numSet:
                    length += 1
                longest = max(longest, length)

        return longest
```