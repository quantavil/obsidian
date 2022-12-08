
Given an array **size[]** of box sizes, our task is to find the number of boxes left at the end, after putting the smaller-sized box into a bigger one.   
_**Note:** Only one small box can fit inside one box._  
**Examples:** 

> **Input:** size[] = {1, 2, 3}   
> **Output:** 1   
> **Explanation:**   
> Here, box of size 1 can fit inside box of size 2 and the box of size 2 can fit inside box of size 3. So at last we have only one box of size 3.
> 
> **Input:** size\[\] = {1, 2, 2, 3, 7, 4, 2, 1}   
> **Output:** 3   
> **Explanation:**   
> Put the box of size 1, 2, 3, 4 and 7 together and for the second box put 1 and 2 together. At last 2 is left which will not fit inside anyone. So we have 3 boxes left. 

**Approach:** The idea is to follow the steps given below:

-   Sort the given array size[] in increasing order and check if the current box size is greater than the next box size. If yes then decrease the initial box number.
-   Otherwise, if the current box size is equal to next box size, then check if the current box can fit inside next to next box size. If yes then move the current box pointing variable, else move next pointing variable further.


```python
"""
for this list [1,2,3,4,5,2,2,2]
step1 : sort the list [1,2,2,2,2,3,4,5] , the length of the list is 8
step2 : checking if the current box is smaller than the next box by above condition
step 3: If any box is able to fit in the other box then we will decrement the box count by 1
"""


def minBox(arr,n):
    arr.sort()
    box = n
    curr_box , next_box = 0,1
    # As curr_box will always be smaller than next_box because the array is sorted therefore it is not necessary
    while (curr_box < n and  next_box < n): 
        print(curr_box,next_box)

        if (arr[curr_box] < arr[next_box]):
            curr_box += 1
            next_box += 1
            box -= 1
        else: # arr[curr_box] == arr[next_box]
            next_box += 1
    return box

print(minBox([1,1,1,1,2,2,2,2,3,3,3,3,4,4,4,4],16))
```