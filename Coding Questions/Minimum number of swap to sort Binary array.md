Steps to be followed:
1. Find the number of zeros to the right side of every 1 and add them.
2. To sort the array, every 1 is to be swap with every 0 on its right side.
3. Hence, the total number of swap operations for a 1 in the array is the number
of zeroes on its right hand side.

```python
def minSwap(arr,n):
    noOfZeros = [0]*n
    count = 0
    # Count number of zeroes on right side of every one.
    noOfZeros[n-1] = 1 - arr[n-1] # if array last element is 0 ? 1 : 0
    for i in range(n-2,-1,-1):
        noOfZeros[i] =noOfZeros[i+1] # if no new 0 find on the right side
        if arr[i] == 0 :
            noOfZeros[i] += 1
    # Count total number of swaps by adding number of zeroes on right side of every one.
    print(noOfZeros)
    for i in range(0, n) :
        if (arr[i] == 1) :
            count = count + noOfZeros[i]
    return  count

arr = [1,0,1,0,0,0,0,1]
n = len(arr)
print(minSwap(arr,n))
```

---

## Alternate Version :
**Minimum Numbers to swaps to make an array summer**
An array A is considered a summer array if all the even values in are on one side and odd values are on the other side.

```python
def minswaps(arr,n):
    count = 0
    evens = 0 # Keeping counts of all even that appear right side of every odds
    for i in range(n-1, -1, -1):
        if arr[i] % 2== 0:
            evens += 1
        else:
            count += evens
    return  count
```