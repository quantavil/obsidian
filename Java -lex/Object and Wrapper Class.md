
-   equals() compares objects to check for equality
    
-   By default, equals() uses memory address to compare objects for equality (just like ==)
    
-   To make it work for different requirements, it needs to be overridden in the classes

-   hashCode() uses an object's data to generate a hash value, which should be a 32 bit integer
    
-   By default, it derives the hash value based on the memory address of the object being used
    
-   If two objects are equal according to the equals() method, hashCode() must produce the same integer value for the two objects
    
-   It is important to understand that if the hash codes of two objects are same, it doesn't prove that the objects are equal, i.e., it is possible for two unequal objects to have the same hash codes. 
    
-   hashCode() uses a formula to generate an integer based on the same attribute
    
-   Any formula can be used for generating the hash code as long as it generates the same value for same objects

##