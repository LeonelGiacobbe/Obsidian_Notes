Link: https://leetcode.com/problems/combination-sum/

### Keys to solve:
- Backtracking
- Since elements can be used more than once, at every point consider two possibilities:
	- We keep using the number
	- We increase the index and use the number at that index, never using the previous number again
- keep a `res` and `sol` array. `sol` contains the numbers currently used to produce the sum that tries to equal the target

### Code
```python
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        res, sol = [], []
        n = len(candidates)

        def backtrack(i, cur_sum):
            if cur_sum == target:
                res.append(sol[:])
                return

            elif cur_sum > target or i == n:
                return
            
            backtrack(i + 1, cur_sum)
            
            sol.append(candidates[i])
            backtrack(i, cur_sum + candidates[i])
            sol.pop()

        backtrack(0, 0)

        return res
```