You are given an integer array A of N elements. A GOOD sub-sequence is : a sub-sequence whose gcd is greater or eequal to K Find the sum of lengths of all possible GOOD sub-sequences

```python
import math
L =[]
def subseq(arr,index,subarr,k):
    if index == len(arr):
        if len(subarr) != 0 and math.gcd(*subarr) >=k:
            L.append(len(subarr))
    else:
        subseq(arr, index + 1, subarr,k)
        subseq(arr, index + 1,subarr+[arr[index]],k)

    return

arr = [2,2,4,5,6,7,8,9,10,200]
subseq(arr,0,[],2)
print(sum(L))
```

Loop through every subsequence instead of recursion
Note: _don’t_ generate a list of subsequences then loop through that
Also that way you can just add to an accumulator and return that from your function
Instead of summing a returned list


```python
def numberOfCarryOperations(a, b):
    # f is the digitSum function
    f=lambda n:sum(map(int,str(n)));return(f(a)+f(b)-f(a+b))/9
```

```cpp
int digitSum(int n)
{
    int sum;
    for (sum=0; n > 0; sum+=n%10,n/=10);
    return sum;
}

int numberOfCarryOperations(int a,int b){
    // a, b >= 0
    return (digitSum(a) + digitSum(b) - digitSum(a+b)) / 9;
}
```
