
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


- [ ] displayMessage() method of Parent invoked
- [ ] displayMessage() method of Child invoked
- [x] Compilation error as final method cannot be overridden
- [ ] displayMessage() method of Parent invoked displayMessage() method of Child invoked


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

  
```java
public class Calculator{
    private int add(int num1, int num2){
        return num1+num2;
    }   
}

public class Tester{
    public static void main(String args[]) {
		Calculator calculator = new Calculator();
		System.out.println(calculator.add(1,2));
	}
}
```

- [ ] 3
- [x] The code will result in a compilation error as the method add cannot be accessed outside the class.
- [ ] The code will not result in a compilation error but will not display any output.
- [ ] The code will result in a compilation error as a non-static method cannot be invoked from a static method.

---
```java
class Employee{
	private int employeeId;
	private static int counter = 1000;
     

	public Employee() {
		employeeId = ++counter;
	}

	public int getEmployeeId() {
		return employeeId;
	}

    public static int getCounter(){
        return counter;
    }
}

public class Tester {
	public static void main(String[] args) {
		Employee employee1= new Employee();
		Employee employee2= new Employee();
		Employee employee3= new Employee();	
        displayEmployeeDetails(employee1);	
        displayEmployeeDetails(employee2);	
        displayEmployeeDetails(employee3);	
	}

    public static void displayEmployeeDetails(Employee employee){
        System.out.println(employee.getEmployeeId() + " " + Employee.getCounter());
    }
}
```

```ad-success
1001 1003 1002 1003 1003 1003
```

---

Which of the following will match the below regular expression?

`String regex = "[A-Z][a-z0-9@$%&]{0,}([ ][A-Za-z]{1,})*";`

```ad-success
alex1
```

---

```java
class Address {
	private int zipCode;

    public Address(int zipCode) {
		this.zipCode= zipCode;
	}

	public int getZipCode() {
		return zipCode;
	}
}

public class Customer {
	public Address address;
	public String name;

	public Customer(String name, int zipCode) {
		this.name = name;
		address = new Address(zipCode);
	}
}

public class Tester{

	public static void main(String args[]) {
		Customer customer = new Customer("Sam",100001);
		// Line 27
	}
}
```


- [ ] System.out.println(this.address.getZipCode());
- [ ] System.out.println(customer.address.zipCode);
- [ ] System.out.println(customer.address.getZipCode());
- [x] Compilation error - not possible to access the zipCode of Address class

---

```java
public class Tester {
	public static void main(String s[]) {
		int[] employeesSalary = { 1350, 2342, 6754, 1200, 1363 };
		int count = 0;
		for (int salary : employeesSalary) {
			switch (salary % 2) {
			default:
				employeesSalary[count] = salary + 1;
			case 0:
				employeesSalary[count] = salary + 1;
				count++;
			case 1:
				employeesSalary[count] = salary + 1;
				break;
			}
		}
		for (int i = 0; i < employeesSalary.length; i++) {
			System.out.print(employeesSalary[i] + " ");
		}
	}
}
```


```ad-success
1351 6755 1201 1364 1363 
```

---

```java
public class Tester {
	public static void main(String args[]) {
		String input1 = "warner";
		String input2 = new String("WARNER");
		input2.toLowerCase();
		if (input1 == input2) {
			System.out.println(" Welcome " + input1);
		} else if (input1.equals(input2)) {
			System.out.println(" Welcome " + input2);
		} else {
			System.out.println("Welcome");
		}
	}
}
```


```ad-success
Welcome
```


----

```java
class Employee{
	public int employeeId;
	private double basicSalary;
	private double totalSalary;
	public Employee(double basicSalary) {
		this.basicSalary = basicSalary;
	}

	public double getBasicSalary() {
		return basicSalary;
	}

	public double getTotalSalary() {
		return totalSalary;
	}

	public int getEmployeeId() {
		return employeeId;
	}

	public double calculateTotalSalary(int bonusPercent) {
		//line 22
		return totalSalary;
	}
}

public class Tester {
	public static void main(String[] args) {
		Employee employee = new Employee(2150);
		employee.employeeId = 101;
		employee.calculateTotalSalary(8);
		// line 32
	}
}
```

You need to help the developer to display the following output by choosing the appropriate code to be implemented in Line 21 and Line 32.

Employee Id: 101, Total salary: 2322.0

Line 21 - this.totalSalary = this.basicSalary * (1 + bonusPercent / 100);

Line 32 - System.out.println("Employee Id: " + employee.employeeId + ", Total salary: " + employee.totalSalary);

- [x] Line 21 - this.totalSalary = this.basicSalary * (1 + (double) bonusPercent / 100);

- [x] Line 32 - System.out.println("Employee Id: " + employee.getEmployeeId()+ ", Total salary: " + employee.getTotalSalary());

---

```java
public class Tester {
	public static void main(String[] args) {
		int num1 = 2, num2 = 20;
		do {
			num2 = num2 / num1;
			if (num1 > num2) {
				break;
			}
			num2--;

		} while (++num1 < 5);

		System.out.println("num1 = " + num1 + " and num2 = " + num2);
	}
}
```

```ad-success
num1 = 4 and num2 = 0
```

---

```java
public class Tester {
	public static void main(String[] args) {
		short discountPercentage = 7;
		int noOfItems = 10;
		float pricePerItem = 255.6f;
		float taxAmount = 135.50f;
		int discountedAmount = (noOfItems * (int) pricePerItem)
				* (1 - discountPercentage / 100);
		double totalAmount = discountedAmount + taxAmount;
		System.out.println("Total amount to be paid is " + totalAmount);
	}
}
```

```ad-success
Total amount to be paid is 2685.5
```

---

```java
class A {
	public int var1;
	public int var2;

	public A(int value) {
		this.var1 = value;
	}

	public int method1() {
		return this.var2;
	}
}

class B extends A {
	public B() {
		super(10);
	}

	public int method1(int value1) {
		return this.var1;
	}
}

class C extends B {

	public C(int value1, int value2) {
		super();
		this.var2 = value2;
	}

	public void method1(int value1, int value2) {
		this.var2 = super.method1(value1);

	}
}

public class Tester {
	public static void main(String args[]) {
		C obj= new C(5, 20);
		System.out.println(obj.method1(5) + obj.method1());

	}
}
```

```ad-success
30
```

---

```java
class Employee {
	public String name;
	public char gender;
	public double salary;

	public Employee(String name, char gender) {
		this.name = name;
		this.gender = gender;
	}

	public Employee(String name) {
		this.name = name;
	}

}

public class Tester {
	public static void main(String[] args) {
		Employee emp1 = new Employee("Robert", 'M');
		Employee emp2 = new Employee("Alex");
		System.out.println(emp2.name + ',' + emp2.gender + ',' + emp1.name);
	}

}
```

```ad-success
Alex,,Robert
```