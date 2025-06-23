Link: https://leetcode.com/problems/longest-substring-without-repeating-characters/


### Keys to solve:
- Use a dict with `sequence: count` pairs
- Iterate l and r pointers together since we're specifically dealing with 10-element long sequences
- Remember the base case (length of `s` less than 10)
- Return all sequences that appear more than once (check value from key)

### Code
```python
class Solution:

	def findRepeatedDnaSequences(self, s: str) -> List[str]:
	
		sequences = set()
        repeated = set()

        if len(s) < 10:
            return []

        l, r = 0, 10
        while r <= len(s):
            if s[l:r] not in sequences:
                sequences.add(s[l:r])
            else:
                repeated.add(s[l:r])
            l += 1
            r += 1

        return list(repeated)
```