Link: https://leetcode.com/problems/palindromic-substrings/

### Keys to solve:
- Account for both even and odd sized palindromes
	- Odd start from one letter
	- Even start from consecutive letters (must be equal)

### Code
```python
class Solution:
    def countSubstrings(self, s: str) -> int:
        palindromes = 0

        for i in range(len(s)):
            palindromes += self.countPalindromes(s, i, i)
            palindromes += self.countPalindromes(s, i, i + 1)

        return palindromes

    def countPalindromes(self, s, l, r):
            res = 0
            while (l >= 0 and r < len(s) and s[l] == s[r]):
                res += 1
                l -= 1
                r += 1

            return res
```