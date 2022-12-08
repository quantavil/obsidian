# Index
1. [[#125 Valid Palindrome]]
2. [[#167 Two Sum II - Input Array Is Sorted]]
<hr style="border:2px solid yellow">

## 125. Valid Palindrome

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        l,r = 0, len(s) -1
        
        while l < r:
            while l<r and not self.alphaNum(s[l]):
                l += 1
            
            while l<r and not self.alphaNum(s[r]):
                r -= 1
            if s[l].lower() != s[r].lower():
                return False
            l,r = l+1, r-1
        return True
        
    def alphaNum(self, c):
        return (ord('A') <= ord(c) <= ord('Z') or
                ord('a') <= ord(c) <= ord('z') or
                ord('0') <= ord(c)  <= ord('9'))
```


```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        r = ""
        for i in range(len(s)):
            if s[i].isalnum() == True:
                r += s[i].lower()
        return r == r[::-1]
```

---
## 167. Two Sum II - Input Array Is Sorted
```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1

        while l < r:
            curSum = numbers[l] + numbers[r]
            if curSum > target:
                r -= 1
            elif curSum < target:
                l += 1
            else:
                return [l + 1, r + 1]
```

![[Screenshot (395).png]]
