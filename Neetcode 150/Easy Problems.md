# Index
1. [[#26 Remove Duplicates from Sorted Array]]
3. [[#80 Remove Duplicates from Sorted Array II]]
4. [[#88 Merge Sorted Array]]
6. [[#238 Product of Array Except Self]]
8. [[#392 is Subsequence]]
9. [[#338 Counting Bits]]
---

## 26 Remove Duplicates from Sorted Array
[[Two-Pointers]] 

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        l = 1
        # here r pointer will traverse through the array
        for r in range(1,len(nums)):
            if nums[r] != nums[r-1] : # We Check if next value is a new value
                nums[l] = nums[r] # if Yes we assign that value at l pointer position
                l += 1
                # for loop will increment right pointer always
        return l
            
```

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        i, j = 1 , 1
        while j < len(nums): # Traversing till the end of list
            if nums[i-1] ==  nums[j]: # if the i pointer value is similar to j pointer we move to next element 
                j += 1
            else:
                nums[i] = nums[j] # else we assign the new found value at which i pointer is
                i += 1
                j += 1
            
        return i  
```

---
## 392 is Subsequence 
[[Two-Pointers]] [[Dynamic-Programming]]
```python

# two pointers solution - O(n) time and O(1) space

def isSubsequence(s, t):

    i, j = 0, 0
    while i < len(s) and j < len(t): # Running the loop while the pointers are in bounds
        if s[i] == t[j]:
            i += 1
        j += 1  # As j will always be incremented regardless of the condition
    return True if i == len(s) else False

```

```cpp
[[include]] <iostream>
[[include]] <string>
using namespace std;

class Solution {
    public:
        bool isSubsequence(string s, string t) {
            int i {0}, j {0};
            while (i < s.length() && j < t.length()) {
                if (s[i] == t[j])
                    i++;
                j++;
            }
            return (i == s.length());
}
};

int main() {
    cout << Solution().isSubsequence("agd", "adhbgdcd") << endl;
    return 0;
}

```
---

## 338 Counting Bits
[[Dynamic-Programming]] [[Bit-Manipulation]]

```python
# Time complexity - O(n) , DP 
class Solution:
    def countBits(self, n: int) -> List[int]:
        dp = [0] * (n + 1)
        offset = 1
        for i in range(1, n + 1):
            if offset*2 == i:
                offset = i
            dp[i] = dp[i - offset] + 1 
        return dp
```

```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        return [bin(i).count('1') for i in range(n+1)]
```

```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> dp (n+1, 0);
            int offset = 1;
            for (size_t i {1}; i < n+1; ++i) {
                if (i == offset*2) {
                    offset = offset*2;
                }
                dp[i] = dp[i-offset] + 1;
            }
            return dp;
    }
};
```
---

## 88 Merge Sorted Array



```python
	# Time complexity: O(nlog(n)) , Space Complexity(O(n)) 
    def merge(nums1: List[int], m: int, nums2: List[int], n: int):
        """
        modify nums1 in-place instead and then sorting it
        """
        for i in range(n):
            nums1[i+m] = nums2[i]
        nums1.sort()
        return nums1

```

```python
def merge(nums1: list[int], m: int, nums2: list[int], n: int)
    """
    Do not return anything, modify nums1 in-place instead.
    """
    # last index of nums1
    last = m+n-1
    # merge in reverse order
    while m>0 and n>0:
        if nums1[m-1] > nums2[n-1]:
            nums1[last] =  nums1[m-1]
            m -=1
        else:
            nums1[last] = nums2[n-1]
            n -=1
        last -=1
    # if there are still elements in nums2, fill nums1 with left over elements of nums 2
    if n>0:
        nums1[:n] = nums2[:n]
    return nums1

```

---

## 80 Remove Duplicates from Sorted Array II

```python

# By using count
# Not using two pointer approach
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        s = set(nums)
        for i in s:
            if nums.count(i) > 2:
                for _ in range(nums.count(i)-2):
                    nums.remove(i)
        return len(nums)
 
```

```python
class Solution:
    def removeDuplicates(self, nums: list[int]) -> int:
        p1,p2 = 1,2
        while p2 < len(nums):
            if nums[p1-1] == nums[p2]:
                nums.pop(p2)
            else:
                p1 += 1
                p2 += 1
        return len(nums)
```

---
## 238 Product of Array Except Self

```python
class Solution:
    def productExceptSelf(self, nums: list[int]) -> list[int]:
        res = []
        p = 1
        q = nums[-1]
        prefix = [p := p*nums[i] for i in range(len(nums))]
        suffix = [0]*len(nums)
        for i in range(len(nums)-1,-1, -1):
            suffix[i] = q
            q = q*nums[i-1]

        for i in range(0,len(nums)):
            if i == 0:
                res.append(suffix[i+1])
            elif i == len(nums)-1:
                res.append(prefix[i-1])
            else:
                res.append(prefix[i-1]*suffix[i+1])
        return res

```

```python
class Solution:
    def productExceptSelf(self, nums: list[int]) -> list[int]:
        """      
        +---+---+---+---+
        | 1 | 2 | 3 | 4 |       Input array  
        +---+---+---+---+

        +---+---+---+---+   <--- Postfix    +----+----+---+---+  ----> Prefix
        | 24 | 12 | 4 | 1 |                 | 1 | 1 | 2 | 6 |
        +---+---+---+---+                   +----+----+---+---+                   
        both are multiplied by each other to get the product of the array
        +------+------+-----+-----+
        | 1*24 | 1*12 | 2*4 | 6*1 |
        +------+------+-----+-----+
        """
        # Time Complexity: O(n)
        # Space Complexity: O(1)
        res = [1] * len(nums)
        prefix = 1
        for i in range(len(nums)):
            res[i] = prefix
            prefix *= nums[i]

        postfix = 1
        for i in range(len(nums)-1,-1,-1):
            res[i] *= postfix
            postfix *= nums[i]
        return res
print(Solution().productExceptSelf([1,2,3,4]))
```

