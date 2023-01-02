## Pass by Value

Whenever a value of a *primitive data type is passed*, the values are copied from the actual parameters to the formal parameters. 
```ad-info
Formal parameters are those parameters that are defined during function definition and Actual parameters are those which are passed during the function call in other Function.
```

This kind of parameter passing is known as **pass by value**. In pass by value, both the actual and formal parameters point to different memory locations and the values are copied in both the memory locations.

```java
class Main {
    public static void main(String[] args) {

        int number = 25;
        System.out.println("Before calling display method = " + number);
        display(number);
        System.out.println("After calling display method = " + number);
    }

    public static void display(int num) {
        num =100;
        System.out.println("Inside display method = "+ num );

    }
}
```
