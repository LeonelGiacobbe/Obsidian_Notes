Link: https://leetcode.com/problems/h-index/


### Keys to solve:
- Make an array of zeros size `len(citations) + 1`
	- for every element in citations increase its index value in that array
	- Make sure to clip to length of array (use `min(length, number)`)
- After that start from the end and iterate until `papers[h] >= h`
### Code
```python
class Solution:

	def hIndex(self, citations: List[int]) -> int:
	
		frequency = [0] * (len(citations) + 1)

		for num in citations:
		
			frequency[min(len(citations), num)] += 1		  
		
		h = len(citations)
		
		papers = frequency[h] 
		
		while papers < h:
		
			h -= 1
			
			papers += frequency[h]
		
		return h

```