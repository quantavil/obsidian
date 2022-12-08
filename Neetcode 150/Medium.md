```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()
        
        for i, num in enumerate(nums):
            if i > 0 and num == nums[i-1]:
                continue
            l, r = i + 1, len(nums) - 1
            while l < r:
                sum = num + nums[l] + nums[r]
                if sum == 0: 
                    res.append([num, nums[l], nums[r]])
                    l += 1
                    while nums[l] == nums[l-1] and l < r:
                        l += 1
                elif sum > 0: 
                    r -= 1
                else:
                    l += 1
        return res
```



```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        mxArea =  0
        l = 0
        while l < len(height):
            r = l+1
            while r < len(height):
                m = min(height[l],height[r])
                area = m * (r-l)
                if mxArea < area:
                    mxArea = area
                r += 1
            l += 1
        return mxArea
```


```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        res = 0
        for l in range(len(height)):
            for r in range(l+1, len(height)):
                area = min(height[l],height[r]) * (r-l)
                res = max(res, area)
        return res
```

