Link: https://leetcode.com/problems/ransom-note/
Language: Python
Topics: [[Hash Tables]]
Keys to solve: 
- Make a `letter:frequency` Hash Table.
	- Iterate through ransom note, decrease `freq` by 1. If letter is not in hashMap, return False.

### Optimal Code:
```Python
class Solution:

    def canConstruct(self, ransomNote: str, magazine: str) -> bool:

        charMap = {} # char : count

  

        for c in magazine:

            if c in charMap:

                charMap[c] += 1

            else:

                charMap[c] = 1

  

        for c in ransomNote:

            if c not in charMap:

                return False

            elif charMap[c] == 1:

                del charMap[c]

            else:

                charMap[c] -= 1

  

        return True
```