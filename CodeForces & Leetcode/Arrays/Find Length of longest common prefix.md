Link: https://leetcode.com/problems/find-the-length-of-the-longest-common-prefix/

### Keys to solve:
- All elements in both arrays are numbers. Use sets to store prefixes
- For every element in `arr1`, add the number to the set, and integer divide that number by 10. That way, with for example `12345`, you store `12345`, `1234`, `123`, `12` and `1`
- For every element in `arr2`, check if the number is in the set, and keep integer dividing by ten while it is not. Keep a `longest` variable.

### Code
```python
class Solution:
    def longestCommonPrefix(self, arr1: List[int], arr2: List[int]) -> int:
        prefixes = set()

        for num in arr1:
            while num:
                prefixes.add(num)
                num //= 10

        longest = 0

        for num in arr2:
            while num and num not in prefixes:
                num //= 10
            if num:
                longest = max(longest, len(str(num)))

        return longest 
```