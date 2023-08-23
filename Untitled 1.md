## Get the highest score
Bob is given an array of N distinct elements and asked to rearrange the elements in this array, so as to maximize the score of the array.

  

Given an array **A** of **N** distinct elements, where **N** is an even number and _A1,A2,A3,A4 . . . A(n-1),A(n)_ are the elements of Array **A,** the score of this Array is **_((A1+A2) x ( A3+A4) x . . . x (A(n-1) + A(n) )_**.

  

Bob can rearrange the array by performing any number of **_swap_** operations.

- In a **_swap_** operation Bob can choose any two elements from the array and swap their positions.

  

Your task is to help bob find the minimum number of swaps required to get the maximum score for the given array.

  

**Note:**

- It is guaranteed that **N** is an **even number** and all the elements are **distinct**.

  

|   |
|---|
|**Input Format**|
|The first line contains an integer, N, denoting the number of elements in AR.|
|Each line i of the N subsequent lines (where 0 ≤ i < N) contains an integer describing AR[i].|

  

|   |
|---|
|**Constraints**|
|1 <= **N** <= 5 x 10^5|
|1 <= **AR[i]** <= 10^9|

|Sample Input|Sample Output|Explanation|
|---|---|---|
|2  <br>1  <br>2|0|No swaps are required [1+2] is the maximum Score|
|2  <br>100  <br>5|0|No swaps are required [100 + 5] is the maximum Score|
|6  <br>4  <br>1  <br>2  <br>9  <br>3  <br>6|2|This can be achieved by 2 swaps. Swap 4 and 9 , After that swap 6 and 4. The new arrangement 9 1 2 6 3 4. Max score possible is [1 + 9] x [6 + 2] x [4 + 3] .|

**Languages**: C#,Python 3,Java,C++,C,Scala,Go,Perl,Bash,Plain JavaScript,R,PHP,Ruby,Python,Clojure

## Another Minimizing Problem
You are given an **array A** of **length N**, representing a line of **stones** such that **each** stone **i** has a bag of **A[i]** **coins** above it.

  

You are going to walk over **all** the stones from 0 to **N-1**. You can start the journey with an initial amount of **coins** equal to **X**. Then, while stepping at **each** stone **i**:

- The value of **X** will be updated as follows: **X = 2 * X - A[i].**

  

Find the **minimum** possible value of **X** to start with **at the beginning**, such that **X >= 0** at any moment.

  

|   |
|---|
|**Input Format**|
|The first line contains an integer, N, denoting the number of elements in A.|
|Each line i of the N subsequent lines (where 0 ≤ i < N) contains an integer describing A[i].|

  

|   |
|---|
|**Constraints**|
|1 <= **N** <= 10^5|
|1 <= **A[i]** <= 10^5|

|Sample Input|Sample Output|Explanation|
|---|---|---|
|2  <br>1  <br>2|1|N = 2 A = [1, 2] starting with X=1 will have the following: =>on stone-0 X will have updated value X=2*X-A[i]=2*1-1=1 =>on stone-1 X=2*1-2=0 X>=0 through all changes, which is valid we can see that we can't start with 0. Hence the answer is 1.|
|3  <br>2  <br>5  <br>6|3|N = 3 A = [2, 5, 6] Starting with X=3: => stone-0 X=2*3-2=4 => stone-1 X=2*4-5=3 => stone-2 X=2*3-6=0 It can be shown that we can not start with a number smaller than 3.|
|3  <br>3  <br>3  <br>3|3|N = 3 A = [3, 3, 3] Start at X=3 The value will stay the same all over the stones. It can't be shown that we can not start with a value smaller than 3.|

**Languages**: C#,Python 3,Java,C++,C,Go,Perl,Bash,Plain JavaScript,R,PHP,Ruby,Python,Clojure


## Good LIS
You are given an array **A** of size **N** and an integer **K**.

  

A **good** subsequence **S****1****, S****2****... S****L**(Where **L** is the length of the subsequence) is a subsequence that has:

- **S****i** **< S****i+1** **(1 <= i < L)**.
- **S****i** **+ k >= S****i+1** **(1 <= i < L)**.
- **A[S****i****] < A[S****i+1****]**.

  

Find the **length** of the **longest good subsequence** you can get.

  

**Notes:**

- A subsequence of array **A** is a sequence that can be derived from array **A** by deleting some or no elements without changing the order of the remaining elements. For example, **[2, 4, 6]** is a subsequence of **[1, 2, 3, 4, 5, 6, 7]** but **[3, 4, 1]** is not.

  

|   |
|---|
|**Input Format**|
|The first line contains an integer, N, denoting the number of elements in A.|
|The next line contains an integer, K, denoting the value K described in the problem.|
|Each line i of the N subsequent lines (where 0 ≤ i < N) contains an integer describing A[i].|

  

|   |
|---|
|**Constraints**|
|1 <= **N** <= 10^5|
|1 <= **K** <= N|
|1 <= **A[i]** <= 10^5|

|Sample Input|Sample Output|Explanation|
|---|---|---|
|4  <br>1  <br>1  <br>3  <br>2  <br>3|2|N = 4  <br>K = 1  <br>A = [1, 3, 2, 3]  <br>  <br>S = [0, 1] can be an optimal answer since  <br>all the conditions are satisfied for all valid i as:  <br>1. S[i]<S[i+1] => {0<1}  <br>2. S[i]+k>=S[i+1]=> {(0+1)>=1}  <br>3. A[S[i]]<A[S[i+1]] => {A[0]<A[1]}  <br>Hence the answer is 2.|
|4  <br>2  <br>1  <br>3  <br>2  <br>3|3|N = 4  <br>K = 2  <br>A = [1, 3, 2, 3]  <br>  <br>S = [0, 2, 3] is the optimal answer since S is satisfying all the given condition in the problem as:  <br>1. 0<2<3 and  <br>2. (0+2)>=2 and (2+2)>=3 and  <br>3. A[0]<A[2]<A[3].  <br>Hence the answer is the length of S which is 3.|
|8  <br>2  <br>1  <br>2  <br>8  <br>2  <br>3  <br>7  <br>4  <br>9|4|N = 8  <br>K = 2  <br>A = [1, 2, 8, 2, 3, 7, 4, 9]  <br>  <br>The optimal answer is  <br>S = [3, 4, 5, 7]  <br>Since S satisfies all the conditions mentioned in the problem.  <br>Hence the answer is 4.|

**Languages**: C#,Python 3,Java,C++,C,Go,Perl,Bash,Plain JavaScript,R,PHP,Ruby,Python,Clojure