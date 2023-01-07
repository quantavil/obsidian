
```java
class A {
	public int count;

	public A() {
		count = 10;
	}

	public int method1() {
		int count = 20;
		return this.count;
	}
}

class B extends A {
	public int method1() {
		return this.count = 15;
	}

	public int method2() {
		return 20;
	}
}

class C extends B {
	public int method2() {
		return 40;
	}
}

public class Tester {
	public static void main(String args[]) {
		A obj1 = new A();
		B obj2 = new B();
		C obj3 = new C();
		System.out.println(obj1.method1() + obj3.method1() + obj3.method2());

	}
}
```

```ad-success
65
```

---

```java
abstract class Employee{

	private String name;

	public Employee(String name) {
		this.name = name;
	}

	public String getName() {
		return name;
	}
}

class SystemEngineer extends Employee{

	public SystemEngineer(String name) {
		super(name);
	}
}

class Tester{

	public static void main(String[] args) {
		Employee systemEngineer = new SystemEngineer("Maria");
		System.out.println(systemEngineer.getName());
	}
}
```

```ad-success
Maria
```

---

Which of the given assertion methods will return true for the code given below?

```java
Student student1 = new Student();
Student student2 = new Student();
Student student3 = student1;
```

The Student class is as follows.

```
public class Student{
    private String name;
}
```

- [x] assertEquals(student1,student2);
- [x] assertEquals(student1,student3);
- [x] assertSame(student1,student3);
- [ ] assertSame(student1,student2);


```ad-note
assertEquals() Asserts that two objects are equal.

assertSame() Asserts that two objects refer to the same object.
```

---
```java
public class Tester {
	public static void main(String[] args) {
		int sum = 0;
		for (int i = 2; i < 8; i += 2) {
			for (int j = 8; j > i; j -= 2) {
				if (i >= j / 2) {
					continue;
				} else {
					sum += i + j;

				}
			}
		}
		System.out.println("Sum = " + sum);
	}
}
```

```ad-success
Sum = 18
```

---

```java
class Validator{
	public int[] studentId = { 101, 102, 103 };

	public void validateStudent(int id) {
		try {
			for (int index = 0; index <= studentId.length; index++) {
				if (id == studentId[index])
					System.out.println("P");
			}
		} finally {
			System.out.println("Q");
		}
	}
}

public class Tester {
	public static void main(String[] args) {
		Validator validator = new Validator();
		try {
			validator.validateStudent(101);
			System.out.print("R");
		} catch (ArrayIndexOutOfBoundsException e) {
			System.out.println("S");
		} finally {
			System.out.println("T");
		}
	}
}
```

```ad-success
PQST
```

---

```java
class Parent{
    public final void displayMessage() {
        System.out.println("displayMessage() method of Parent invoked");
    }
}

class Child extends Parent{
    public void displayMessage() {  
        System.out.println("displayMessage() method of Child invoked");
    }
}

public class Tester{
    public static void main(String[] args) {
        Parent parent = new Child();
        parent.displayMessage();
    }
}
```


```ad-failure
displayMessage() method of Parent invoked displayMessage() method of Child invoked
```

---

Which of the following are invalid variable declarations?

  
- [ ] double salary = 123467;
- [x] int 1value = 2147483648;
- [x] char gender = "M";
- [ ] long bonus = 35000L;
- [x] boolean flag = False
- [x] String name = 'Alex'

---

How many instance variables, reference variables and objects are there in the code given below?

```java
class Student {
	public int studentId;
	public String name;
}

public class Tester {
	public static void main(String[] args) {
		Student s1 = new Student();
		Student s2 = new Student();
		Student s3 = s1;
	}
}
```

```ad-success
instance variables : 2, reference variables : 3, objects: 2

```

---

```java
public class Tester {
	public static void main(String[] args) {
		System.out.println(demo(5, 1));
	}

	public static int demo(int x, int y) {
		if (x == 0)
			return 1;
		else if (y > x)
			return 0;
		else
			return (y + demo(x - 1, y + 1));
	}
}
```

```ad-success
6
```

---

Which of the following statements is/are false?

- [x] A class can extend only one class or implement only one interface.
- [x] Methods declared in an interface are implicitly public and abstract.
- [x] Data fields declared in an interface are implicitly public, static and final.
- [x] A class can implement an interface using extends keyword.

---
Which of the following are valid identifiers? 

- [ ] break$
- [ ] _9Number
- [x] middle_Name
- [ ] default
- [ ] Class
- [ ] $ dept

---

```java
class Calculator {
	public int num1 = 10;
	public float num2 = 20;
	public double sum;
	public double product;

	public double add(int num1, int num2) {
		double sum = this.num1 + this.num2;
		return sum;
	}

	public double multiply(int num1, int num2) {
		double sum = this.add(num1, num2);
		double product = this.sum * this.num1;
		return (int) product;
	}
}

public class Tester {
	public static void main(String[] args) {
		Calculator c = new Calculator();
		System.out.println(c.multiply(10, 5));
	}

}
```

```ad-success
0.0
```

---

```java
public class Tester {
	public static void main(String[] args) {
		int num1 = 28;
		int num2 = 36;
		int num3 = 0;
		if (~(num2 / num1) < 0 && (num1 + num2) % 4 == 0) {
			num1 = num1 + --num3;
		}
		if ((num2 / num1) > 1 || num3 == 0) {
			num1 = num1 + num3++;
		    System.out.println(num1 + --num3);
		} else {
			System.out.println(num1 + --num3);
		}
	}
}
```

```ad-success
25
```

---

```java
public class Tester {
	public static void main(String[] args) {
		int num1 = -20;
		int num2 = -30;
		int num3 = 10;
		int num4 = -40;
		if (num1 + num2 >= num4) {
			if (num4 < num3) {
				if (num4 % num3 != 0) {
					System.out.println(1);
				} else {
					System.out.println(2);
				}
			}
		} else {
			if (num2 / num1 > 0) {
				if (num1 < num2 || num4 % num3 == 0) {
					System.out.println(3);
				} else {
					System.out.println(4);
				}
			}
		}
	}
}
```

```ad-success
3
```

---

