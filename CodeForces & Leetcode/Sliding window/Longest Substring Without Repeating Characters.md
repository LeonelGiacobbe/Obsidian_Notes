Link: https://leetcode.com/problems/longest-substring-without-repeating-characters/


### Keys to solve:
- create a set (can't have duplicates)
- Use two pointers `l` and `r`
- Add letters until there is a duplicate in the set
	- Once there is, start removing from the left
- Take the max out of all the substrings found 

### Code
```python
class Solution:

	def lengthOfLongestSubstring(self, s: str) -> int:
	
		letters = set()
		
		l = 0
		
		res = 0
		
		for r in range(len(s)):
		
			while s[r] in letters:
		
				letters.remove(s[l])
		
				l += 1
		
		letters.add(s[r])
	
		res = max(res, r - l + 1)	
		
		return res

```