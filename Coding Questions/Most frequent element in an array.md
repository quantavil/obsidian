
### Python
---
```python
# Time complexity: O(n^2) and Auxiliary Space: O(1)

def mostFreq(arr,n):
	# Sorting is not required 
    maxCount  = 0
    for i in range(n):
        count = 0
        for j in range(n):
            if arr[i] == arr[j]:
                count += 1
        if  count > maxCount:
            maxCount = count
            maxElement = arr[i]
    return maxElement
```

---
```python

# Time complexity: O(nlog(n)) and Auxiliary Space: O(1)


def mostFreq(arr,n):
    # We first sort the array, then linearly traverse the array.
    arr.sort()
    max_count = 1; res = arr[0]; curr_count = 1

    for i in range(1, n):
        
        if (arr[i] == arr[i-1]):
            """if arr = [1,2,3,4]
        It will check check 2 ,1 and 3,2 and 4,3"""
            curr_count += 1
        else:
            if (curr_count > max_count):
            # It will not check of ending ones [11,11,11,7,7,7,7,7,] as 7 will not be check because above statement will always be true.
                max_count = curr_count
                res = arr[i-1]
            curr_count = 1
    # After ending the loop if still the current count is greater than max count 
    if (curr_count > max_count):
        max_count = curr_count
        res = arr[n-1]
    return res

```
---

```python
curr_max = 0
curr_value = None

for x in my_list:
	if my_list.count(x) > curr_max:
		curr_max = my_list.count(x)
		curr_value = x
print(f"The value {curr_value} is repeated : {curr_max} times")
```

---

```python
from collections import Counter

counter = Counter(my_list)
print(counter.most_common(1))
```

---

```python
most_freq = max(set(my_list), key=my_list.count)
freq = my_list.count(most_freq)

print(most_freq, freq)
```

---

### C++

