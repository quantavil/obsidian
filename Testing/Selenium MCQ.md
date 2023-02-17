
- [[#Selenium Basic|Selenium Basic]]
- [[#Selenium Advanced|Selenium Advanced]]
- [[#Java|Java]]

## Selenium Basic

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

4. The following code has been written to handle expired SSL certificates in firefox. The Firefox profile created for this is " Selenium" . The code is not able to handle the expired SSL certificate. Identify the error in the code. 

```

ProfilesIni prof = new ProfilesIni();
FirefoxProfile ffProfile = prof.getProfile("Selenium");

ffProfile.setAcceptUntrustedCertificates(false);
ffProfile.setAssumeUntrustedCertificateIssuer(true);
driver = new FirefoxDriver();
driver.manage().window().maximize();
		
```

*setAssumeUntrustedCertificateIssuer should be set as False*
*setAcceptUntrustedCertificates needs to be set as True*

5. Select the correct sequence in which maven searches for the dependency specified in pom.xml.

a) search in http://repo1.maven.org/maven2/  
b) search in remote repository   
c) search in ~/m2./repository  
d) throws error unable to find dependency 

*c-a-b-d*

6. Which axis method selects all the parent, grandparent till the root node of an element?

*Ancestor*

7. The following code is written in the **BasePage** class of a test following POM design pattern, to invoke internet explorer in the node machine.

```

DesiredCapabilities cap = DesiredCapabilities.internetExplorer();
cap.setBrowserName("ie");
String Node ="http://<<ip of node>>:<<port no>>/wd/hub";
driver = new RemoteWebDriver(new URL(Node), cap);
```

While executing the code in the node, the following error is popping up: 

```

Caused by: org.openqa.selenium.WebDriverException: The best matching driver provider org.openqa.selenium.edge.EdgeDriver can't create a new driver instance for Capabilities
```

Choose the change to be made in the code snippet above.

*cap.setBrowserName("internet explorer");*

8. Consider the following class:

```

public class NewTest 
{
  @Test(groups={"action1"})
  public void f()
  {System.out.println("f");
  }
  @Test(groups={"action2"})
  public void f1()
  {System.out.println("f1");
  }
  @BeforeSuite
  public void beforeSuite()
  {System.out.println("b4 suite");
  }
  @AfterSuite
  public void afterSuite() {
System.out.println("after suite");
  }
}
```

Consider the following testng.xml.

```

<suite name="Suite">
  <test name="Test">
   <groups>
<run>
 	<include name="action1"/>
</run>
</groups> 
<classes>
   <class name="test.NewTest" /> 
</classes>
  </test> <!-- Test -->
</suite> <!-- Suite -->
```

What will be the output getting displayed in the console ?

*f*

9. Identify the number of files, which would be created, and the maximum size of files , if the below mentioned tags are written in **Log4j.xml** file.

```

<appender name="file" class="org.apache.log4j.RollingFileAppender">
	    <param name="append" value="false" />
	    <param name="maxFileSize" value="1KB" />
	    <param name="maxBackupIndex" value="2" />
	    <param name="file" value=".\\Logs\\AppLogs.log" />
	    <layout class="org.apache.log4j.PatternLayout">
		<param name="ConversionPattern" value%d{ISO8601} %5p %F [%t] %c{1}:%L - %m%n />
	    </layout>
	</appender>
```


no of files: 3, maximum File size: 1 KB

10. Which of the following statements are true about  log4j.properties file?

*The log4j.properties file is a log4j configuration file which keeps properties in key-value pairs.*

*By default, the LogManager looks for a file named log4j.properties in the CLASSPATH.*

11. Which of the following log4j objects are responsible for publishing logging information to various preferred destinations?

*appenders*

12. Identify the console output after executing the below methods through the testng.xml file. 

Consider the following  testmethods in the TestNG file: 

```

@Test(groups = {"Light"})
public void color1 () {
        System.out.println("white");
}

@Test(groups = {"Dark" })
public void color2() {
	System.out.println("Red");
}

@Test(groups = {"Medium"})
public void color3() {
	System.out.println("Orange");
}
```

The TestNG Xml file is defined as below: 

```

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite name="Suite">
  <test name="Test">
   <groups> 
  <define name="Colours">
  <include name="Light"/>
  <include name="Dark"/>  
   <include name="Medium"/>  
  </define>  
  <run>
  <include name="Colours"/> 
<exclude name="Medium"></exclude>
  </run> 
  </groups>
    <classes>
      <class name="Demo.Demo06_TestNG_Grouping"/>
    </classes>
  </test> <!-- Test -->
</suite> <!-- Suite -->
```


*white,Red*

13. Choose the correct xpath expressions to identify the Radiobutton named "Business".(Choose two)

```

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

14. Consider the XML file given below.

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

Assuming that  **Coastal** is the context node, identify the output of the XPath given below.

```

count(ancestor::*)
```


*2*

15. What will be the  execution status of the method **test2** in the TestNG dashboard, once you execute the below mentioned code?

```

String assertionString="demoforHardAssertion";
@Test
public void test2()
 {
    //Soft assert Object
	
    SoftAssert softAssert=new SoftAssert();
	softAssert.assertEquals("demoforHardAssertions", assertionString);
	
    System.out.println("After Assert equals");
	
    softAssert.assertTrue(assertionString.equals("demoforHardAssertions"));
    System.out.println("After Assert true");
	
    }
```

*pass*

16. Arrange the below testng.xml tags from parent to child?

```
 <test>  
 <suite>  
 <class>  
 <methods>  
 <classes>
```


`<suite> <test> <classes> <class> <methods>`

17. The following code has been written to handle expired SSL certificates in InternetExplorer. The code is not able to handle the expired certificate.  Identify the error in the code.

```

DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.setCapability(CapabilityType.ACCEPT_SSL_CERTS, true);
System.setProperty("webdriver.ie.driver","IEDriverServer.exe");
WebDriver driver = new InternetExplorerDriver();
```

*Desired capabilities object is not used while initializing webdriver instance.*

18. In a maven project, you have to configure **log4j.properties** files in such a way that the logs get generated according to the specified pattern layout. Identify the set of tags you need to include in the **pom.xml** file. 

`<resources> <resource> <directory>src/main/resources</directory> <includes> <include>log4j.properties</include> </includes> </resource> </resources>`


19. Consider a scenario where you have two @Test methods in your class  
a)**login**  
b)**buyProducts**

Due to Invalid credentials, **login** @Test method fails.

Assuming that the login method has **priority** "**1**" assigned to it, how can you skip the execution of **buyProducts** method when **login** fails (Since **buyProducts** can only be executed after **Login**)?

*@Test((priority=2,dependsOnMethods={"Login"})) public void buyProduct(){ //code to buyProduct }*

20. Set the correct hierarchy of log levels order in Log4JLogging 

*TRACE < DEBUG < INFO < WARN < ERROR < FATAL*

21. You are working with JDBC drivers to fetch results from a My SQL database. You have the following code which is throwing a compilation error. Identify the error in the code . (Assume that connection is successfully established with the database)

```

ResultSet resset=stmt.executeQuery("select * from Test");
while(resset.previous())
{
	System.out.println("Username: "+resset.getString(1));
	System.out.println("password : "+resset.getString(2));
}
```

*next() method should be used instead of previous()*

---
---

## Cucumber

1. Below is the feature file written by Sam. Complete the file with the correct missing code from below options.

```
Feature: Login action

Scenario Outline: Successful login with valid credentials

Given User is on home page

When User navigate to login page

And user enters “<username>” and “<password>”

Then message displayed as login successfully.
```

`Examples: |username|password| |testuser1|test@123| |testuser2|test@345|`

2. In an application there are two functionalities, “My Finance” and “My Dashboard”. There is common requirement of “Login” as a first action for both the functionalities. You have to generate the scenarios for both of these. What is the best option to use, which will reduce the code redundancy in this case?

	*Cucumber hooks*

3. Suppose, we need to make sure that the login functionality is working for all types of subscription holders. That requires execution of login multiple times. Which structure it is, from Gherkin language?

*Scenario Outline*

4. In a Maven test project if you are adding dependency for selenium, in ‘pom.xml’ file, what does it means?

*This will indicate, which selenium jar files are to be downloaded from the central repository to local repository.*

5. In a feature file, there are three scenarios defined. Then two hooks are added @Before and @After. How many times the hooks will get executed if you run the feature file?

*Both for three times*

6. John has created a feature file for an application, registration page. How he should run the feature file to generate the snippet?

*Run as- Cucumber feature*

7. If you have not mentioned below line in the runner class, what will happened at the time of execution?

@RunWith(Cucumber.**class**)

*You will not able to run since there is no option available to run as “Junit test”*

8. If there is any compilations errors in feature file or step definition file, you will see which option?

*Cucumber features –dry-run*

9. Which of the below will generate a HTML report at the location mentioned in the formatter itself?

*format = {“html:Folder_Name”}*

10. When will the below hook run?

@Before(“@Smoke”)

Public void beforetest(){

System.out.prinyln(“This is before loop.”);

}

*This will run only before the Smoke scenario in feature file*

11. 