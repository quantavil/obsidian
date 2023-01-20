## Referential Arrays

Python represents a list or tuple instance using an internal storage mechanism of an array of object references.
At the lowest level, what is stored is a consecutive sequence of memory addresses at which the elements of the sequence reside.

![[Pasted image 20230120094213.png]]

`counters = [0]*8` , , all eight cells of the list reference the same object
![[Pasted image 20230120094315.png]]

![[Pasted image 20230120094347.png]]
## Compact Arrays
