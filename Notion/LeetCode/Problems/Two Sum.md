---
Difficulty: Easy
Category: Hash Table
Language: Python
Status: Done
---
# Question

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to_ `_target_`.

You may assume that each input would have _**exactly**_ **one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

  

# Solution

> [!important]  
> Main Idea: use two iterate variables, i from 0 and j from i+1, check if (nums[i] + nums[j] == target)  

```Python
class Solution(object):
    def twoSum(self, nums, target):
        index = 0
        indices = []
        for i in range(len(nums)):
            for j in range(i+1, len(nums)):
                if(nums[i] + nums[j] == target):
                    indices.append(i)
                    indices.append(j)
            index += 1

        return indices
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
```