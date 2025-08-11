Link: https://leetcode.com/problems/coin-change/

### Keys to solve
- DO NOT USE GREEDY APPROACH
- Iterate over `(1, amount)` at every step, check if that amount is greater than any of the available coins.
	- If it is, then the current smallest amount of coins will be `min(dp[amount], dp[amount - valOfCoin] + 1)`
		- The logic is, if we do use that coin, then the overall amount will be `1 + dp[a -valOfCoin]`, and we only take it if its smaller than the current minimum
### Code
```python
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [float('inf')] * (amount + 1)

        dp[0] = 0
        for a in range(1, amount + 1):
            for c in coins:
                if a - c >= 0:
                    dp[a] = min(dp[a], dp[a - c] + 1)

        return dp[amount] if dp[amount] != float('inf') else -1
```