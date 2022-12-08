

# std::transform
![[conthier.gif]]xx
C++ Algorithm **transform()** function is used in two different ways:

**1. unary operation**:- This method performs unary operation **op** on the elements in range [first1, last1] and stores the result in range starting from **result**.

This transform() applies a function to each element of a range:

![C++ Algorithm transform Function](https://static.javatpoint.com/cpp/images/cpp-algorithm-transform-function.png)

**2.Binary operation**:- This method performs binary operation **binary_op** on the elements in range [first1, last1] with the elements in the range starting with iterator **first2** and stores the result in range starting from **result**.

This transform() takes two 2 ranges and applies a function that takes 2 parameters, on each couple of elements from the input ranges:

![C++ Algorithm transform Function](https://static.javatpoint.com/cpp/images/cpp-algorithm-transform-function2.png)

## Syntax

1. **Unary operation(1)**
```cpp
template <class InputIterator, class OutputIterator, class UnaryOperation>

OutputIterator transform (InputIterator first1, InputIterator last1,  
OutputIterator result, UnaryOperation op);
```

2. **Binary operation(2)**
```cpp
template <class InputIterator1, class InputIterator2,  
class OutputIterator, class BinaryOperation>  

OutputIterator transform (InputIterator1 first1, InputIterator1 last1,InputIterator2 first2, OutputIterator result,BinaryOperation binary_op);  
```

## Parameter

**first1**: An input iterator pointing the position of the first element of the first range to be operated on.

**last1**: An iterator pointing the position one past the final element of the first range to be operated on.

**first2**: Input iterator pointing to the first element in the second range to be operated on.

**result**: An output iterator to the initial position of the range where the operation results are stored.

**op**: Unary function applied to each element of the range.

**binary_op**: Binary function that two elements passed as its arguments.

## Return value

transform() returns an iterator pointing to the end of the transformed range.

## Complexity

Complexity is linear in the distance between first1 and last1.

## Example

```cpp
[[include]] <iostream>    
[[include]] <algorithm>    // std::transform
using namespace std;

// Unary function applied by the transform function
int op_increment (int x) { 
  x = x + 1;
  return x; 
}

int main () {
  int n = 5;        // Number of elements in the array.
  int input_array[] = {3, 6, 8, 13, 2};
  int output_array[n];    // The array that will store out result
  std::cout << "Input array:";
  for(int i=0; i<5; i++){
    cout << ' ' << input_array[i];
  }
  cout << '\n';

  // The function takes start and end positions of the
  // range on which we want to apply our function. It
  // also takes the starting position of our output
  // array and the function we want to apply to the array.
  transform (input_array, input_array+5, output_array, op_increment);
 
  std::cout << "The output array now contains:";
  for(int i=0; i<5; i++){
    cout << ' ' << output_array[i];
  }
  cout << '\n';

  return 0;
}
```

> [! Output]
> Input array: 3 6 8 13 2
The output array now contains: 4 7 9 14 3

```cpp
[[include]] <iostream>     
[[include]] <algorithm>    // std::transform
[[include]] <vector>       // std::vector
using namespace std;

// Binary function applied by the transform function
int op_add (int i, int j) { 
  return i+j; 
}

int main () {
  int n = 5;
  int arr1[] = {1, 2, 3, 4, 5};
  int arr2[] = {6, 7, 8, 9, 10};
  int output[n];

  std::cout << "Input array1:";
  for(int i=0; i<n; i++){
    cout << ' ' << arr1[i];
  }
  cout << '\n';
  std::cout << "Input array2:";
  for(int i=0; i<n; i++){
    cout << ' ' << arr2[i];
  }
  cout << '\n';
  
  // The transform function takes start and end position
  // of first array, start position of second array,
  // start position of output array and the binary
  // function to apply to the input arrays.
  std::transform (arr1, arr1+n, arr2, output, op_add);

  std::cout << "Output array:";
  for(int i=0; i<5; i++){
    cout << ' ' << output[i];
  }
  cout << '\n';

  return 0;
}
```

> [!Output]
> Input array1: 1 2 3 4 5
Input array2: 6 7 8 9 10
Output array: 7 9 11 13 15

---
