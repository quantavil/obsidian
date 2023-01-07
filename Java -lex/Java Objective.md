
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
- [ ] int 1value = 2147483648;
- [ ] 
- [ ] char gender = "M";
- [ ] 
- [ ] long bonus = 35000L;
- [ ] 
- [ ] boolean flag = False
- [ ] 
- [ ] String name = 'Alex'