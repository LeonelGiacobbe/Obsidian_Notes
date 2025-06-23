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
		
		  
		# Checks for odd-length palindromes (l and r start from same letter)
		while (l >= 0 and r < len(s) and s[l] == s[r]):
		
			if (r - l + 1 > length):
		
				palindrome = s[l:r+1]
		
				length = r - l + 1
		
			r += 1
			
			l -= 1
		# Set l and r pointers to consecutive letters to test even length
		l, r = i, i + 1
	
	  
	# Do the same check as before, but now with l and r being consecutive
	while (l >= 0 and r < len(s) and s[l] == s[r]):
	
		if (r - l + 1 > length):
		
			palindrome = s[l:r+1]
			
			length = r - l + 1
		r += 1
		
		l -= 1
	
	  
	
	return palindrome

```