Link: https://leetcode.com/problems/minimum-window-substring/

### Keys to solve
- Need to use two dictionaries to keep track of letter frequencies
- Need to be smart about the way you check whether or not the sub-string is valid.
	- Should have a `have` and `need` variable. `need` is the length of `s`. `have` starts at 0
		- when iterating over `s`, if that char is in `t's` dictionary and the frequency in s's dictionary is greater than or equal to t's dictionary, increase `have` by 1
			- Whenever this condition breaks because of the moving `l` pointer, decrease `have` by 1.

### Code
```python
class Solution:
    def minWindow(self, s: str, t: str) -> str:
        # if t is empty, return that
        if t == "": return ""

        # dicts to count freq of both s and T
        countT, window = {}, {}

        # populate T dictionary
        for char in t:
            countT[char] = 1 + countT.get(char, 0)

        # how many chars have at least the required freq, and how many
        # do not
        have, need = 0, len(countT)

        #base results
        res, resLen = [-1, -1], float("infinity")

        #left pointer
        l = 0

        #moving right pointer
        for r in range(len(s)):
            # update S dictionary
            char = s[r]
            window[char] = 1 + window.get(char, 0)

            # if the character is also in T and now the freq >= freq(char in T)
            # increase have by 1
            if char in countT and window[char] == countT[char]:
                have += 1

            # While all chars have at least the required frequency
            while have == need:
                # Check to see if we've found a shorter substring
                if r - l + 1 < resLen:
                    resLen = r - l + 1
                    res = [l, r]
                
                # move left pointer, decrease freq of that letter
                window[s[l]] -= 1

                # if that movement made the freq drop below the necessary,
                # decrease have, since we cant check of the reqs for that char
                if s[l] in countT and window[s[l]] < countT[s[l]]:
                    have -=1

                # move left pointer forward
                l += 1

        l, r = res
        return s[l: r + 1] if resLen < float("infinity") else ""

            
```