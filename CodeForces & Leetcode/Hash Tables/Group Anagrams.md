Link: https://leetcode.com/problems/group-anagrams/


### Keys to solve:
- make a  `string: list of strings` has map
- Sort string (makes all anagrams the same)
	- If sorted string is in hash map, add the original string to the value list
	- If it's not, create an entry
- Iterate over the dict and add the lists to an overall list

### Code
```python
class Solution:

	def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
	
	words = { }

	for i, word in enumerate(strs):
	
		sorted_str = ''.join(sorted(word))
	
		if sorted_str not in words:
			words[sorted_str] = [word]
	
		else:
			words[sorted_str].append(word)
	
	result = []
	
	for element in words:
	
		result.append(words[element])
	
	return result

```