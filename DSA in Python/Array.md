## Referential Arrays

Python represents a list or tuple instance using an internal storage mechanism of an array of object references.
At the lowest level, what is stored is a consecutive sequence of memory addresses at which the elements of the sequence reside.

![[Pasted image 20230120094213.png]]

`counters = [0]*8` , , all eight cells of the list reference the same object
![[Pasted image 20230120094315.png]]

However, we rely on the fact that the referenced integer is immutable. Even a command such as counters[2] += 1 does not technically change the value of the existing integer instance. This computes a new integer, with value 0+1, and sets cell 2 to reference the newly computed value.
![[Pasted image 20230120094347.png]]
## Compact Arrays

The type code allows the interpreter to determine precisely how many bits are needed per element of the array.

![[Pasted image 20230120094624.png]]

```python
import sys
from array import array

a =  array('I',[2,3,5,7,11,13,17,19,2,3,5,7,11,13,17,19])
b = [2,3,5,7,11,13,17,19,2,3,5,7,11,13,17,19]
print(" Size Of a : {0}".format(sys.getsizeof(a)))
print(" Size Of b : {0}".format(sys.getsizeof(b)))

```

> [!Output]
>  Size Of a : 144
 > Size Of b : 184
 
## Dynamic Array

Dynamic array is that a list instance maintains an underlying array that often has greater capacity than the current length of the list. For example, while a user may have created a list with five elements, the system may have reserved an underlying array capable of storing eight object references (rather than only five). This extra capacity makes it easy to append a new element to the list by using the next available cell of the array. 

If a user continues to append elements to a list, any reserved capacity will eventually be exhausted. In that case, the class requests a new, larger array from the system, and initializes the new array so that its prefix matches that of the existing smaller array. At that point in time, the old array is no longer needed, so it is reclaimed by the system. Intuitively, this strategy is much like that of the hermit crab, which moves into a larger shell when it outgrows its previous one

## Efficiency of Python’s Sequence Types