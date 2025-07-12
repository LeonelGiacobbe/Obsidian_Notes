Link: https://leetcode.com/problems/find-median-from-data-stream/


### Keys to solve
- Use binary search to find the right index to insert the new element at
- When finding median, consider even and odd length lists. For even, you need `midIndex - 1, midIndex`

### Code
```python
class MedianFinder:

    def __init__(self):
        self.numList = []
        

    def addNum(self, num: int) -> None:
        # Use binary search to get index position and insert
        l, r = 0, len(self.numList)

        while l < r:
            m = (l + r) // 2
            if num > self.numList[m]:
                l = m + 1
            else:
                r = m     

        insertPosition = l
        self.numList.insert(insertPosition, num)   

    def findMedian(self) -> float:
        # If size is odd, len // 2
        # if even: mid + mid + 1 // 2
        if not self.numList or len(self.numList) == 0:
            return None
        if len(self.numList) % 2 != 0:
            midIndex = len(self.numList) // 2
            return self.numList[midIndex]
        else:
            leftMidIndex = len(self.numList) // 2 - 1
            rightMidIndex = len(self.numList) // 2
            return (self.numList[leftMidIndex] + self.numList[rightMidIndex]) / 2
```