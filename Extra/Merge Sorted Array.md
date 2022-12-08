```python
def merge(nums1, nums2):
    """
    merge two sorted array , not inplace , as the list size increases
    """
    i,j = 0,0
    while i < len(nums1) and j< len(nums2):
        if nums1[i] < nums2[j]:
            i += 1
        else:
            nums1.insert(i, nums2[j])
            j+=1
            i+=1
```
---

```python

def merge(nums1,m, nums2, n):
	"""
	merge two sorted array into one sorted array, in temp array , not inplace
	"""
    temp = []
    i,j = 0,0
    while i < m and j < n:
        if nums1[i] < nums2[j]:
            temp.append(nums1[i])
            i += 1
        else:
            temp.append(nums2[j])
            j += 1
    if i < m:
        temp.extend(nums1[i:])
    if j < n:
        temp.extend(nums2[j:])
    return temp

```
---
```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
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
    
```