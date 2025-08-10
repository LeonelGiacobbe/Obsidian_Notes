	Link: https://leetcode.com/problems/word-break/

### Keys to solve:
- Bottoms up dp approach
- We assign the last element as True and then backtrack to see if any word in `wordDict` can get us to that last element. If it can, that position is also marked as true. We do that for every index in `s`. If at the end, `dp[0]`  is true, that means there is a combination of words in `wordDict` that can be used to recreate `s`
### Example:
`s = "leetcode", wordDict = ["leet","code"]`
we iterate e->d->o->c->t->e->e->l
for every letter, we check if any word in `wordDict` is smaller than the amount of letters between the current index and the end of `s`. If it is, we can check. When getting to `c`, we see that `s[i: i + len("code")] == "code"`, so `dp[4] = dp[4 + len("code")] = True`, then, we continue until we get to l, where we see  `s[i: i + len("leet")] == "leet"
so `dp[o] = dp[0 + len("code")] = True`, so overall result is True
### Solution
```python
class Solution:
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:
        # Assume all but last case is false
        dp = [False] * (len(s) + 1)
        # Last case is true because it'd mean that we found a 
        # combination of w in wordDict that got us to the end of the
        # string
        dp[len(s)] = True

        # Start from end of string backwards
        for i in range(len(s) - 1, - 1, -1):
            for w in wordDict:
                # Check size to see if we can even compare strings
                # if we can, compare. 
                if (i + len(w) <= len(s) and s[i : i + len(w)] == w):
                    dp[i] = dp[i + len(w)]
                if dp[i]:
                    break

        return dp[0]

```