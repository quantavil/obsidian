1. Which of the below annotations will be run once after all methods in the class?
	*@AfterClass*

2. Rina used findElements method to identify the elements,what type of the exception will be thrown when the element is not found ?
	*NoSuchElementException*

3. What is the difference between 'close' and 'quit' methods in WebDriver?
	*'Close' method closes the main browser window but the 'quit' method closes all the browser windows including popups.*

4. Which of the following selenium component enables simultaneous running of tests in multiple browsers and environments?
	*GRID*

5. Which of the below operator is used to allocate memory to array variable in Java?
	*new*

7. Which of the following is **NOT** a valid exception that you would come across in Selenium WebDriver?
	*NoSuchElementFoundException*


8. If in the WebDriver code, you set the implicit wait as 10sec. Then it will be set for:

	*For the life of the WebDriver object instance*


9. The ___ collection object is used to store unique values of strings in a variable

```html
set<String>
```


11. Which of the following exceptions is not ideal to be handled(ignore) via FluentWait?
	*TimeoutException*

12. In your WebDriver script, If you happen to click on a link that launches a separate window, which of the below statements will help you to work with window of your choice before locating elements within it?
	*driver.switchTo().window(windowname)*


14. The ___ regular expression is used to match any single character except new line character?
	*Dot (.)*
15. Which of the following is **NOT** a valid exception that you would come across in Selenium WebDriver?
	*NoSuchElement*

16. When there are 2 identical  link objects on the webpage, which one of them is clicked and returned when link-text or partial text is used to locate them?
	*Clicks on the first match as per the HTML source code and ignores the next.*

17. Which statement is the correct way to maximize the browser in a WebDriver test script?
	*driver.manage().window().maximize();*

18. Which type of 'Wait' is active as long as the WebDriver object is active?
	*Implicit wait*

19. In an application, suppose you have the dynamically generated Identifier for an element. The next time when page is loaded and you are performing click operation on that element, what will happen?
	*The click operation will fail with an “element not found” error*
20. Which of the following is **NOT** a valid WebElement method to select an option from drop-down list?
	*SelectByID*

21. Where will you use setup() and teardown() methods and make it run once for all the tests in the class?
	*Use @BeforeClass annotation before all tests and @AfterClass after all tests.*

22. Which method should you use when you want to verify whether a certain check box is selected in Web driver Selenium?
	*isSelected()*

23. Which of the following WebDriver commands will you use to check the presence of a web element?
	*verifyElementPresent*


---

1. Arrange the following scrum events as per the chronological sequence (first to last) in which they are conducted.

  
1. Sprint plan  
2. Daily scrum meeting  
3. Sprint review meeting   
4. Sprint retrospective   
5. Sprint

1, 3, 2, 4, 5

1, 5, 2, 4, 3

1, 2, 5, 4, 3

1, 5, 2, 3, 4

2. In an agile project, what would you call a chart that contains the progress of stories done over time and is used to track the project progress?
	*Burn-up Chart*


---

1. When can a scrum team mark a project done?

Development is done 

Testing is done

Defects are fixed and working as expected 

*All the above*

2. In Test Planning and Design Phase, which technique is called as ' Branch Testing or Control Flow Testing '.
 
 *Decision Coverage*

3. Which of the following works as a single team structure in Agile?

*Scrum*

4. *Sanity testing* is a kind of Software Testing performed after receiving a software build, with minor changes in code, or functionality, to ascertain that the bugs have been fixed and no further issues are introduced due to these changes

5. At a UI review meeting of PetFit - The Pet Lovers App! — the SRS document was required to add the following comment on Typography; these elements need to be defined in one central place and then used across the system you're designing." Which of the following the above comment satisfy?

 *Unambiguity*

6. Which of the lollowrng statements are false?

	1. Selenium WebDriver supports browser compatibility testing
	2. getPageSourcet()) method of org.openqa.selenium.WebDriver returns a list of strings `(List<String>)`
	3. quit() closes only the currently active browser window while close() closes all browser Windows
	4. close() closes only the currently active browser window while quit() closes all browser Windows
	*2 abd 3*

7. In a web application if any element is without class, name, or id attribute, then how could it be located?
	*By Xpath*

8. Which of the following activities are a part of the Test Execution and Implementation?
	1.Creating test suits from the test cases
	2.Writing a test summary report
	3.Designing the tests 
	4.Executing test cases either manually or by using test execution tools
	*1,3,4*

9. In Jenkins terminology, which of the following combination gives an accurate information.
	A. Master
	B. Slave ;

	i. System in which testing tools are available and no Jenkins instance is running
	ii. System in which no Jenkins instance is running and no testing tool is installed
	iii. System in which Jenkins instance is installed

	*A->iii , B->ii*

10. Whenever any step is required to perform in each scenario then those steps needs to be placed in
	*Background*

11. Which notation describes the specific context/initial conditions of the acceptance test? '
	*Given* 

12. Which of the following is/are the disadvantages of Agile methodology?
	*Poor resource planning and documentation
	 Level  collaboration is difficult
	Time-to-Market*

13. Choose the challenges of the Selenium
	 *Selenium supports only windows based applications .*

14. Which one of the following cannot be used as an element Iocator in Selenium Web Driver?
	*Style*

15. Mary wants to locate a checkbox "Emailupdates" from a certain website. She wants to verify whether the checkbox is visible or not 
	*if (emailUpdates.isEnabled() && emaiIUpdates.isDisp|ayed())*

16. 
*Chrome: webdriver.chrome.driver
Internet explorer: webdriver.ie.driver
Firefox: webdriver.gecko.driver*

17. In Test Planning and Design Phase, which technique is called as ' Branch Testing or Control Flow Testing '.
	*Decision Coverage*


---

## Selenium Advanced

1. After updating the dependency in pom.xml file in a maven project, the JRE used is automatically getting changed to JRE 1.5.  Which configurations needs to be added in the pom.xml to continue using JRE1.8 to build the project ?   
 
```
<properties> <maven.compiler.source>1.8</maven.compiler.source> <maven.compiler.target>1.8</maven.compiler.target> </properties>
```


```
<plugins> <plugin> <groupId>org.apache.maven.plugins</groupId> <artifactId>maven-surefire-plugin</artifactId> <version>2.12.4</version> <configuration> <!-- Suite testng xml file to consider for test execution --> <suiteXmlFiles> <file>testng.xml</file> </suiteXmlFiles> <source>1.8</source> <target>1.8</target> </configuration> </plugin> </plugins>
```


2. 
Choose the correct xpath expressions to identify the Radiobutton named "Business".(Choose two)
```html
<form id="fromRegisterPopUP"" name="fromRegisterPopUP"">
    <div style="text-align:left;">
    <div style="margin-top:10px;">
        <label style="float:left;">
        <div class="register_row">
            <input class="post_ad_field_r" type="radio" value="Individual"/>
            <input class="post_ad_field_r" type="radio" checked="checked" value="Business"/>
```


`//form/div[2]/div/input[2]`

`//*[@id='fromRegisterPopUP']/div[2]/div[1]/input[2]`


3. Consider the XML file given below.

```
<?xml version="1.0" encoding="UTF-8"?>
<Transportation>
	<Water>
		<Inland />
		<Coastal>
			<Yacht />
			<Cruise />
			<Cargo />
		</Coastal>
	</Water>
	<Air>
		<Domestic />
		<International />
	</Air>

	<Land>
		<Highway />
		<Railway />
	</Land>

</Transportation>
```

Assuming that **water** is the context node, identify the output of the Xpath given below.
```
count(following::*)
```

	*7*

4. 



