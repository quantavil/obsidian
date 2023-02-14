1. Which of the below annotations will be run once after all methods in the class?
@AfterTest

2. Rina used findElements method to identify the elements,what type of the exception will be thrown when the element is not found ?
	*NoSuchElementException*

3. What is the difference between 'close' and 'quit' methods in WebDriver?

'Close' method clears the browser memory while the 'quit' method closes the browser window.

'Close' method closes the browser but the 'quit' method additionally removes the connection to the server.

'Close' method closes the main browser window but the 'quit' method closes all the browser windows including popups.

4. Which of the following selenium component enables simultaneous running of tests in multiple browsers and environments?
	GRID


5. Which of the below operator is used to allocate memory to array variable in Java?
	*new*

6. Where will you use setup() and teardown() methods and make it run once for all the tests in the class?

Use @Before annotation before all tests and @After after all tests.

Use @BeforeTest annotation before all tests and @AfterTest after all tests.

Use @BeforeClass annotation before all tests and @AfterClass after all tests.

None of the above

7. Which of the following is **NOT** a valid exception that you would come across in Selenium WebDriver?
	*StaleElementReferenceException*

8. If in the WebDriver code, you set the implicit wait as 10sec. Then it will be set for:

For all the objects in the test script

For the life of the WebDriver object instance

Only the current class

Throughout all the test scripts in that test suite

9. The ___ collection object is used to store unique values of strings in a variable

list<String>

list<WebElements>

set<String>

set<WebElements>

10. When there are 2 identical  link objects on the webpage, which one of them is clicked and returned when link-text or partial text is used to locate them?

Neither of them. Selenium will throw an error as two similar objects are there.

Clicks on the first match as per the HTML source code and ignores the next.

Clicks on both the matching links one after another, in the order they occur in the HTML source code.

Clicks on the final match as per the HTML source code and ignores the next.

11. Which of the following exceptions is not ideal to be handled(ignore) via FluentWait?

NoSuchElementException

TimeoutException

ElementNotVisibleException

NoAlertPresentException

12. In your WebDriver script, If you happen to click on a link that launches a separate window, which of the below statements will help you to work with window of your choice before locating elements within it?



driver.getwindowhandles(windowname)