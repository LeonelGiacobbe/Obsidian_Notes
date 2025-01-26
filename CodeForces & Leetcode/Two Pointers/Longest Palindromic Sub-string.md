Link: https://leetcode.com/problems/longest-palindromic-substring/

### Keys to solve:
- odd and even-length palindromes
- Iterate over every letter in the string:
	- use that (and the following letter) as pivots.
	- Two pointers `l` and `r` that expand away from pivot as long as they are equal

### Code
```python
	class Solution:
	
	def longestPalindrome(self, s: str) -> str:
	
	for i in range(len(s)):
	
		l, r = i, i
		
		  
		
		while (l >= 0 and r < len(s) and s[l] == s[r]):
		
			if (r - l + 1 > length):
		
				palindrome = s[l:r+1]
		
				length = r - l + 1
		
			r += 1
			
			l -= 1
		
		l, r = i, i + 1
	
	  
	
	while (l >= 0 and r < len(s) and s[l] == s[r]):
	
		if (r - l + 1 > length):
		
			palindrome = s[l:r+1]
			
			length = r - l + 1
		r += 1
		
		l -= 1
	
	  
	
	return palindrome

```