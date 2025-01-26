Link: https://leetcode.com/problems/happy-number/


### Keys to solve:
- create a set (can't have duplicates)
- perform addition of square digits to set
	- At every iteration, check if not on set
		- If it is, then we detect a loop
	- If at some point n == 1, return True

### Code
```python
	class Solution:

		def SumSquares(self, n: int) -> int:
		
			sum = 0
			
			while n:
			
				digit = n % 10
				
				digit = digit ** 2
				
				sum += digit
				
				n = n // 10
		
			return sum
		
		def isHappy(self, n: int) -> bool:
		
			# for each iteration, add to hash map to check for loops
			
			visit = set()
			
			while n not in visit:
			
				visit.add(n)
			
				n = self.SumSquares(n)
			
				if n == 1:
				
					return True
			
			return False

```