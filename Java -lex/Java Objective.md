
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

assertEquals(student1,student2);

assertEquals(student1,student3);

assertSame(student1,student3);

assertSame(student1,student2);