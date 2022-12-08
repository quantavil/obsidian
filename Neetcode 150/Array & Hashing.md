# Index
1. [[#217 Contains Duplicate]]
2. [[#242 Valid Anagram]]
3. [[#1 Two Sum]]
4. [[#49 Group Anagrams]]
5. [[#347 Top K Frequent Elements]]
6. [[#238 Product of Array Except Self]]
7. [[#36 Valid Sudoku]]
8. [[#659 Encode and Decode Strings]]
9. [[#128 Longest Consecutive Sequence]]

<hr style="border:2px solid yellow">

## 217. Contains Duplicate
[[Easy]] [[Array]] [[Hash-Table]]  [[Sorting]]
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()
        for n in nums:
            if n in hashset:
                return True
            hashset.add(n)
        return False
```

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        i,j = 0,1
        while j < len(nums):
            if nums[i] == nums[j]:
                return True
            else:
                i += 1
                j += 1
        return False
```

---

## 242. Valid Anagram
[[Easy]] [[Hash-Table]] [[Sorting]] 
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        SMap , TMap = {}, {}
        if len(s) != len(t):
            return False
        for i in range(len(s)):
            SMap[s[i]] = SMap.get(s[i],0) + 1
            TMap[t[i]] = TMap.get(t[i],0) + 1
        for j in SMap:
            if SMap[j] != TMap.get(j,0):
                return False
        return True
            
        
```

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        SMap = {c: s.count(c) for c in set(s)}
        TMap = {c: t.count(c) for c in set(t)}
        return SMap == TMap
        
```

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s) == Counter(t)
        
```

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return True if sorted(s) == sorted(t) else False
```

---
## 1. Two Sum
 [[Easy]] [[Array]] [[Hash-Table]] 
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> list[int]:
        hashmap = {}  # value : index
        for i , n in enumerate(nums):
            diff =  target - n
            if diff in hashmap:
                return [hashmap[diff],i]
            hashmap[n] = i 
        return []
```

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> list[int]:
        for i in range(len(nums)):
            n =  target - nums[i]
            if n in nums[i+1:]:
                j = i+1
                while j < len(nums):
                    if nums[j] == n:
                        return [i,j]
                    j += 1
        return []
```

---
## 49. Group Anagrams
[[Medium]] [[Hash-Table]]  [[String]] [[Sorting]] 
```python
class Solution:
    def groupAnagrams(self, strs: list[str]) -> list[list[str]]:
        
        res = defaultdict(list) # mapping charCount to list of Anangrams
        
        for s in strs:
            count = [0] * 26
    
            for c in s:
                count[ord(c) - ord('a')] += 1
            res[tuple(count)].append(s) # As count is list and in python list cannot be keys, we use tuple as key
        return res.values()
```

```python
class Solution:
    def groupAnagrams(self, strs: list[str]) -> list[list[str]]:
        
        res = {} # mapping charCount to list of Anangrams
        
        for s in strs:
            word = ''.join(sorted(s))
            if word not in res:
                res[word] = [s]
            else:
                res[word].append(s) # we are appending the list object
        return [v for v in res.values()]
```


```python

class Solution:
    def groupAnagrams(self, strs: list[str]) -> list[list[str]]:
        
        res = defaultdict(list) # mapping charCount to list of Anangrams
        
        for s in strs:
            res[''.join(sorted(s))].append(s)
        return res.values()
```

---
## 347. Top K Frequent Elements
[[Medium]] [[Array]] [[Hash-Table]] [[Bucket-Sort]] [[Heap]] 

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        """
        +--------+---+-----+-----+-------+---+---+---+
        | Count  | 0 |  1  |  2  |   3   | 4 | 5 | 6 |
        +--------+---+-----+-----+-------+---+---+---+
        | Values |   | [3] | [2] | [1,4] |   |   |   |
        +--------+---+-----+-----+-------+---+---+---+

        """
        count = {}
        freq = [[] for _ in range(len(nums) + 1)]
        for n in nums:
            count[n] =  count.get(n,0) + 1
        for key, value in count.items(): # It will return key, value pair for every number and count
            freq[value].append(key)
        res = []
        for i in range(len(freq) - 1, 0, -1):    # [[], [3], [2], [1, 4], [], [], [], [], [], []] but in reverse order
            for n in freq[i]:
                res.append(n)
                if len(res) == k:
                    return res

```

---
## 238. Product of Array Except Self
[[Medium]]  [[Array]] 

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

```python
class Solution:
    def productExceptSelf(self, nums: list[int]) -> list[int]:
        res = []
        p = 1
        q = nums[-1]
        suffix = [0]*len(nums)
        prefix = [p := p*nums[i] for i in range(len(nums))]
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

---
## 36. Valid Sudoku
[[Medium]] [[Array]]  [[Hash-Table]]  [[Matrix]]

```python
class Solution:
    def isValidSudoku(self, board: list[list[str]]) -> bool:
        cols  = defaultdict(set)
        rows  = defaultdict(set)
        boxes = defaultdict(set) # key = (r//3, c//3) it will form unique key for boxes
        for r in range(9):
            for c in range(9):
                if board[r][c] == '.':
                    continue
                num = board[r][c]
                box_idx = (r//3, c//3)
                if num in rows[r] or num in cols[c] or num in boxes[box_idx]:
                    return False
                rows[r].add(num)
                cols[c].add(num)
                boxes[box_idx].add(num)
        return True
```

```python
class Solution:
    def isValidSudoku(self, board: list[list[str]]) -> bool:
        # Checking if 1D array is valid
        def isValid(arr):
            seen = set()
            for i in arr:
                if i != '.':
                    if i in seen:
                        return False
                    seen.add(i)
            return True
        
        # row wise check
        for row in board:
            if not isValid(row):
                return False
        
        # column wise check
        for j in range(9):
            col = [board[i][j] for i in range(9)]
            if not isValid(col):
                return False
        
        # 3x3 grid check
        for i in range(0,9,3):
            for j in range(0,9,3):
                grid = [board[k][l] for k in range(i,i+3) for l in range(j,j+3)]
                if not isValid(grid):
                    return False
        return True
```

---
## 659. Encode and Decode Strings
[[String]] [[Arrays]]
```python
class Solution:
    """
    @param: strs: a list of strings
    @return: encodes a list of strings to a single string.
    """
    def encode(self, strs):
        res = ""
        for s in strs:
            res += str(len(s)) + ":" + s
        return res

    """
    @param: str: A string
    @return: dcodes a single string to a list of strings
    """
    def decode(self, str):
        res =  []
        i = 0
        while i < len(str):
            j = str.find(":", i)    # This line can be replace by
									# j = i
						            # while str[j] != ":":
					                # j += 1
            a = j+1 # start of the string
            b = j+ int(str[i:j]) + 1 # end of the string
            res.append(str[a:b])
            i = b # move to the end of the string
        return res
```

---
## 128. Longest Consecutive Sequence
[[Medium]] [[Array]] [[Hash-Table]] 

```python
class Solution:
    def longestConsecutive(self, nums: list[int]) -> int:
        """
        +----------+----+---+---+---+----------+-----+----------+-----+
        |          | 1  | 2 | 3 | 4 |          | 100 |          | 200 |
        +----------+----+---+---+---+----------+-----+----------+-----+
        | No left  |    |   |   |   | No Left  |     | No left  |     |
        | Neighbor |    |   |   |   | Neighbor |     | Neighbor |     |
        +----------+----+---+---+---+----------+-----+----------+-----+
        """

        numSet = set(nums)
        max_counter = 0
        for n in numSet:
            if n-1 not in numSet:
                current_counter = 1
                while n+1 in numSet:
                    current_counter += 1
                    n += 1
                max_counter = max(max_counter, current_counter)
        return max_counter
```

```python
class Solution:
    def longestConsecutive(self, nums: list[int]) -> int:
        nums.sort()
        max_counter  = 0
        current_counter = 0
        for i in range(len(nums)):
            if i == 0:
                current_counter = 1
            elif nums[i] == nums[i-1]:
                continue
            elif nums[i] == nums[i-1] + 1:
                current_counter += 1
            else:
                max_counter = max(max_counter, current_counter)
                current_counter = 1
        return max(max_counter, current_counter)
```

---
