1. In software engineering, behavior-driven development is an Agile software development process that encourages collaboration among developers, QA and non-technical or business participants in a software project.
2. Feature file is written in : *Gherkin* is the format for cucumber specifications. It is a domain specific language which helps you to describe business requirements.
3. A Feature File is an entry point to the Cucumber tests. This is a file where you will describe your tests in Descriptive language. The feature file is the essential segment of cucumber tool, which is used to write acceptance steps for automation testing
4. Pick the correct statements with respect to step definition file.

	- [x] A step definition file can be created from the execution of feature file. 
	- [ ] All the step definitions should be given in a single file
	- [ ] Cucumber throws error if the step definition doesn't match with the Gherkin step
	- [x] Step definitions aren’t linked to a particular feature file or scenario 
	*Explanation* : On the execution of feature file, you will be able to generate step definition statements.

5. What is a runner class?

	- [ ] Runner class contains the main method to execute the test.
	- [x] In a runner class you can specify feature files to be picked up plus the steps definitions location,using some annotations. 
	- [ ] Runner class describes the test scenarios.
	- [x] Cucumber Uses Runner class of JUnit framework 
	Explanation : By the usage of tags, we can execute specified scenarios. we can also generate different type of reports

	Explanation : Runner class will use the Junit annotation @RunWith(), which tells JUnit what is the test runner class


---

1. If you are using multiple @Test annotations in a single JUnit file, and the methods c_test, a_test, and b_test are there which not arranged alphabetically in the code. Then in which sequence they will be executed?
  

The testrunner runs the methods in alphabetical order !!

Depends as testrunner treats all methods to be independent of each other

Runs the methods in random order during each test run

All of the above

2. What is the difference between WebDriver close and quit methods?

Nothing, these methods are interchangeable.

close method clears the browser memory and the quit method closes the browser window.

close method closes the browser but the quit method additionally removes the connection to the server.

close method closes the main browser window but the quit method closes all the browser windows including popups.!!

3. Which of the below Annotation runs once after all methods in the class?


@Test

@BeforeTest

@AfterClass

@BeforeClass

4. Pick the odd one out for getWindowHandles() or getWindowHandle() methods of webdriver?


getWindowHandle gets the address for the browser that has the current focus

getWindowHandles gets the address of all open browsers

The return type for both the methods is a list object

5. Select the correct selenium webdriver statement to work with Iframes?


driver.switchTo().frame(ID of the frame);

driver.switchTo().frame(name of the frame);

driver.switchTo().frame(0); // where 0 is the index of the frame

All of the above !!

6. The ___ collection object is used to store unique values of strings in a variable


List

Iterator
 
Set !!

Collection

7. Assume that you created a HTML page with hyperlinks and later noticed that there are multiple matches.  What will be the result if you have used either linkText or PartiallinkText?


It selects all the matches

It selects only the last matches.

It selects the first match !!

It will generate an error.

8. Assume that there are 2 identical  link objects on a web page. Which of the link is selected when link-text or partial text is used?

Throws error as 2 similar objects are there

clicks on last match

clicks on first match !!

clicks on both the links simultaneously

9. Choose the incorrect option on difference between final and finally key word in Java? 

Final class can't be inherited, final method can't be overridden and final variable value can't be changed

You can use finally without a try block but catch block is a must !!

Finally keyword is used to execute a block of code compulsorily whether an exception is handled or not.

Finally block follows a try or catch block

10. What functionality does WebDriver support on browser cookies?

A. add and delete an individual cookie

B. delete all cookies

Both A & B !!

none of the above

11. The below is the html source code for a textbox object on a webapplication  
    Choose the CSS selector to identify the object uniquely.  
  <input name="search" title="Search" class="txtbox" id="q" onkeyup="return autoComplete(event);"  
   onclick="clearSearchText('q')" type="text" value="Search"/>

input.txtbox[value="Search"]

input.txtbox[type="Search"]

input.q[value="Search"]

input.q[type="Search"]

12. If you happen to click on a link that launches a separate window in an application,and in webdriver during reply which of the below commands helps to work with window of your choice before locating elements within it.

driver.switchto().window(windowname)  !!

driver.switchto(windowname)

driver.getwindowhandles(windowname) 

driver.moveto(windowname)

12. Multiple inheritance in Java is achieved through

By using the extend keyword in the child class

By using Abstract class

By using Interfaces

By using polymorphism concept of object oriented programming language

13. What is the output of the below code. The textbox webelement is created with name as txt1

driver = new InternetExplorerDriver();  
        driver.get(url);  
        WebElement objUName=driver.findElement(By.name("txt"));  
        try {  
            if (objUName.isEnabled())  
                objUName.sendKeys("Welcome");  
        }catch(NoSuchElementException e){  
            System.out.println(e.toString());  
        }

You cannot use WebElement in webdriver.

The code will execute successfully and it enters the value into the textbox.

The code will execute successfully but the textbox will not have any value.

The code will generate the error “No such Element present”