-   **@BeforeMethod and @AfterMethod** – These annotations run before and after each test method
-   **@BeforeClass and @AfterClass** – These annotations run once before and after the first _@test_ method in a class
-   **@BeforeTest and @AfterTest** – The BeforeTest annotation runs before the _@BeforeClass_ annotation and the AfterTest annotation runs after the _@AfterClass_ annotation
-   **@BeforeSuite and @AfterSuite**– These annotations run before and after any test annotated method in a class respectively. These annotations start the beginning of a test and the end of it, for all the classes in a suite

Talking about the execution order of these annotations, they execute in the below order:

**_@BeforeSuite -> @BeforeTest -> @BeforeClass -> @BeforeMethod -> @Test -> @AfterMethod -> @AfterClass -> @AfterCTest -> @AfterSuite_**

```ad-info
The key point to remember is apart from _@BeforeMethod_ and _@AfterMethod_, all other annotations run only once, whereas the _@BeforeMethod_ and _@AfterMethod_ run post every _@Test_ method.
```


## Advantage of TestNG over JUnit

1.  TestNG Annotations are easy to understand over JUnit.
2.  No constraints like declaring @BeforeClass and @AfterClass in TestNG, which are present in JUnit.
3.  As method name constraint is present in JUnit, such method name constraint is not present in TestNG and you can specify any test method names.
4.  TestNG enables you to group test cases easily which is not possible in JUnit.
5.  TestNG supports following three 3 additional setUp/tearDown level: @Before/AfterSuite, @Before/AfterTest and @Before/AfterGroup.
6.  TestNG do not require extend any class. 
7.  TestNG allows to execute test cases based on group which isn't possible in JUnit.
8.  Parallel execution of Selenium test cases is possible in TestNG.

## **TestNG Assertions**

Like JUnit, TestNG provides multiple level assertions to validate your actual results against your expected results. Few of the commonly used assertions are:

1.  **assertTrue**– This assertion verifies whether the defined condition is true or not. If true, it will pass the test case. If not, it will fail the test case
    
    ```java
    Assert.assertTrue(condition);
    ```
    
2.  **assertFalse**– This assertion verifies whether the defined condition is false or not. If false, it will pass the test case. If not, it will fail the test case
    
    ```java
    Assert.assertFalse(condition);
    ```
    
3.  **assertEquals**– This assertion compares the expected value with the actual value. If both are the same, it passes the test case. If not, it fails the test case. You can compare strings, objects, integer values etc. using this assert
    
    ```java
    Assert.assertEquals(actual,expected);
    ```
    
4.  **assertNotEquals**: This is just opposite to what assertEquals does. If actual matches the expected, the test case fails, else the test case passes
    
    ```java
    Assert.assertNotEquals(actual,expected,Message);
    ```
    

An important part to note in assertions is that your tests will not execute to the next line of code if your assertions failed. It will automatically jump to the next test annotated method.

