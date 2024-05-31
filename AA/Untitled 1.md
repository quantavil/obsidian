### 1. What is Selenium?

Selenium is an open-source tool used as a free automation testing suite of tools. Licensing is not required, and it has more benefits than other testing tools. The tests can be done in any operating system like Mac, Linux and Windows. Selenium can be combined with some tools, such as TESTNG in Selenium and JUNIT, for managing test cases and generating reports.

### 2. What are the Selenium suite components?

**Selenium IDE**

It is a Firefox/Chrome plug-in that was developed to speed up the creation of automation scripts. It records the user actions on the web browser and exports them as a reusable script.

**Selenium Remote Control (RC)**

RC is a server that allows users to write application tests in various [programming languages.](https://www.simplilearn.com/tutorials/programming-tutorial/first-programming-language "programming languages.") The commands from the test script are accepted by this server and are sent to the browser as Selenium core [JavaScript](https://www.simplilearn.com/tutorials/javascript-tutorial/introduction-to-javascript "JavaScript") commands. The browser then behaves accordingly.

**Selenium WebDriver**

WebDriver is a programming interface that helps create and run test cases. It makes provision to act on web elements. Unlike RC, WebDriver does not require an additional server and interacts natively with the browser applications.

**Selenium Grid**

The grid was designed to distribute commands to different machines simultaneously. It allows the parallel execution of tests on different browsers and different operating systems. It is exceptionally flexible and is integrated with other suite components for simultaneous execution.

### 3. Mention the advantages of using Selenium as an automation tool.

Selenium is an automation tool and has some unique benefits that give it a competitive edge over others such as open source, multi-language support, platform support, multi-browser support, framework availability and flexibility, reusability, and integrated and parallel test execution.

### 4.  What is test automation or automation testing?

Test automation or automation testing is the process of using specialized software to control the execution of tests and compare the results with expected outcomes. Automation testing can help reduce the time, cost, and effort required to test software applications by automating repetitive tasks and allowing testers to focus on more critical test cases. 

### 5.  What are the advantages of automation testing?

There are many advantages of automation testing. Perhaps the most obvious is that it can save you a lot of time and effort. Automation testing can help to speed up the process of testing by automating repetitive tasks, such as running the same test cases multiple times or across different browsers.

Another big advantage is that automation testing can improve the accuracy of your tests. By automating the process, you can eliminate human error and ensure that your tests are always carried out the same way. This can be particularly important when testing complex applications where there is a greater risk of errors.

Finally, automation testing can also help to improve the coverage of your tests. By automating more of the testing process, you can increase the number of test cases that are run and cover a larger range of functionality. This can help to ensure that your software is thoroughly tested and free of bugs.

### 9. What are the testing types supported by Selenium? 

Selenium supports Regression testing and Functional testing. 

Regression testing - It is a full or partial selection of already executed test cases that are re-executed to ensure existing functionalities work fine.

The steps involved are - 

1. Re-testing: All tests in the existing test suite are executed. It proves to be very expensive and time-consuming.
2. Regression test selection: Tests are classified as feature tests, integration tests,  and the end to end tests. In this step, some of the tests are selected.
3. Prioritization of test cases: The selected test cases are prioritized based on business impact and critical functionalities.

Functional testing - Functional Testing involves the verification of every function of the application with the required specification. 

The following are the steps involved:

1. Identify test input
2. Compute test outcome
3. Execute test
4. Compare the test outcome with the actual outcome 

### 10. What are the different types of annotations which are used in Selenium?

Different types of annotations that are used in Selenium include:

- @Test - This annotation is used to mark a method as a test method
- @BeforeMethod - This annotation is used to execute a method before each test method
- @AfterMethod - This annotation is used to execute a method after each test method
- @BeforeClass - This annotation is used to execute a method before the first test method

### 12. Mention the types of Web locators.

Locator is a command that tells Selenium IDE which GUI elements ( say Text Box, Buttons, Check Boxes, etc) it needs to operate on. Locators specify the area of action.

Locator by ID: It takes a string parameter which is a value of the ID attribute which returns the object to findElement() method.

  driver.findElement(By.id(“user”));

Locator by the link: If your targeted element is a link text then you can use the by.linkText locator to locate that element.

  driver.findElement(By.linkText(“Today’s deals”)).click();

Locator by Partial link: The target link can be located using a portion of text in a link text element.

  driver.findElement(By.linkText(“Service”)).click();

Locator by Name: The first element with the name attribute value matching the location will be returned.

  driver.findElement(By.name(“books”).click());

Locator by TagName: Locates all the elements with the matching tag name

  driver.findElement(By.tagName(“button”).click());

Locator by classname: This finds elements based on the value of the CLASS attribute. If an element has many classes then this will match against each of them. 

  driver.findElement(By.className(“inputtext”));

Locator by XPath: It takes a parameter of String which is a XPATHEXPRESSION and it returns an object to findElement() method.

  driver.findElement(By.xpath(“//span[contains(text(),’an account’)]”)).getText();

Locator by CSS Selector: Locates elements based on the driver’s underlying CSS selector engine.

  driver.findElement(By.cssSelector(“input#email”)).sendKeys(“myemail@email.com”);