Selenium is a suite of tools which can automate actions on web browsers. Each tool is developed to support a specific kind of automation approach.

### The three important tools that form the core of selenium ecosystem are

**Selenium IDE**
-   Users are new to selenium and/or have no prior knowledge in programming.
-   Automated test scripts have to be created in the quickest possible way.
-   Cross-browser testing is not possible
- Selenium IDE cannot be integrated with any other tools

**Selenium WebDriver**
-   Skilled programmers, who can handle code using object-oriented APIs, are available.
-   Test automation involves complex functionalities liek UIs built using HTML5, AJAX and also while testing in headless browsers (HTMLUnit).
-   Developing advanced automation frameworks which needs features like
    -   Customized results reporting
    -   Portability across browsers and operating systems.
- Selenium WebDriver tests can be integrated with tools like Cucumber , JIRA, Jenkins

```ad-info
Selenium IDE is User Interface (UI) based solution for recording and playing back tests on web pages. Whereas Selenium WebDriver is an Application Programming Interface (API) based solution for programming and executing tests on web pages.
```


**Selenium Grid**
-   Multiple tests have to be run in parallel on multiple machines to reduce overall execution time.
-   Tests need to be distributed across multiple machines to check for application compatibility with different OS-Browser combinations.

## JUnit framework Annotation

**@Test**
This annotation tells the JUnit framework that the method attached to it can be run as a test case. Hence every test case method in the class must be attached with its own @Test annotation.

**@Before**
This annotation tells the JUnit framework that the method attached to it must be run once before executing every @test method that is there in the class. It is used to allocate resources that are needed by all the test methods in the class.  
Some of the tasks that are done in @Before method include create temporary variables, setting default values, invoking the test environment, etc.

**@After**
This annotation tells the JUnit framework that the method attached to it must be run once after executing every @test method that is there in the class.  
It is used to release all the resources allocated by the @Before method.

**@BeforeClass**
This annotation tells the JUnit framework that the method attached to it must be run only once before any other method in the class is executed.  
It is used to execute resource intensive computational tasks that need to be done only once for all tests such as connecting and opening a database, etc.

**@AfterClass**
This annotation tells the JUnit framework that the method attached to it must be run only once after all other methods in the class have been executed.  
It is used to close or release resources that were allocated by the @BeforeClass method.
