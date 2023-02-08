What is Selenium ?
Selenium is an open-source framework to automate and perform software testing such as smoke tests, integration tests, etc. on web applications. It provides a playback/recording tool and domain-specific language.

  
Driver Initialization Basics:  
⦁ Chrome WebDriver driver = new ChromeDriver();  

Driver Initialization Advanced:  
⦁ System.setProperty(“webdriver.chrome.bin”,“path/to/chrome/binary”);  
              ChromeProfilefp= new ChromeProfile();

⦁ File file=new File(“path/to/extension.xpi”);  
       fp.addextension(file)

Selenium Locators:  Selenium locators are used to find and match the webpage elements   
i. Locating by ID:  
       driver.findElement(By.id("q")).sendKeys("Se lenium 3");  
ii. Locating by Name:  
          driver.findElement(By.name("q")).sendKeys ("Selenium 3");  
iii. Locating by Xpath:  
           driver.findElement(By.xpath("//input[@id='q'])).sendKeys("Selenium 3");  
iv. Locating Hyperlinksby Link Text:  
driver.FindElement(By.LinkText("edit this page")).Click();  
v. Locating by DOM:  
dom =document.getElementById('signinForm')  
vi. Locating by CSS:  
      driver.FindElement(By.CssSelector("#rightbar> .menu >li:nth-of-type(2) > h4"));  
vii. Locating by ClassName:  
 driver.findElement(By.className("profileheader"));  
viii. Locating by TagName:  
driver.findElement(By.tagName("select")).C lick();   
ix. Locating by LinkText:  
driver.findElement(By.linkText("NextP age")).click();  
x. Locating by PartialLinkText:  
 driver.findElement(By.partialLinkText(" NextP")).click();

Selenium Navigators:  The navigator interface in selenium helps in moving backward and forwards in the browser’s history

a. Navigate to URL:  
driver.get(“http://newexample.com”)  
driver.navigate().to(“http://newexample.com”)

b. Refresh page:  
driver.navigate().refresh()

c. Navigate forwards in browser history:  
 driver.navigate().forward()

d. Navigate backward in browser history:   
      driver.navigate().back()

  
JUNIT: JUNIT (Java Unit Testing Tool) is a framework used to perform unit-level testing.   
⦁ @Test: test method to run with public void return type  
⦁ @After: method to run after the test method  
⦁ @AfterClass: method to run before the test method  
⦁ @Before: method to run before the test method  
⦁ @BeforeClass: method to run once before any of the test methods in the class have been executed  
⦁ @Ignore: This annotation is used to ignore a method

  
TestNG: TestNG is an open-source framework for automated testing. The NG in TestNG stands for Next Generation. It is similar to Junit but with more functionality to offer.

⦁ @test: This annotation marks a class or method as a part of a test  
⦁ @BeforeSuite: This annotation makes sure that the method only run once before all the tests have run  
⦁ @AfterSuite: This annotation makes sure that the method runs once after the execution of all the tests  
⦁ @BeforeTest: This annotation will make sure that the method marked with this annotation runs before the first method annotated with @test  
⦁ @AfterTest: This annotation will make sure that the method marked with this annotation runs after all the methods annotated with @test execute all the classes inside <test> tag in the testng.xml file.  
⦁ @BeforeGroups : A method annotated with this annotation will run before all the first test methods run in that specific group  
⦁ @AfterGroups: A method annotated with this annotation will run after all the test methods run in that specific group  
⦁ @BeforeClass: A method annotated with this annotation will run only once per class and before all the first test methods run  
⦁ @AfterClass: A method annotated with this annotation will run only once per class and after all the test methods run  
⦁ @BeforeMethod: A method annotated with this annotation will run before every @test annotated method  
⦁ @AfterMethod: A method annotated with this annotation will run after every @test annotated method

  
Windows: Sometimes the web applications may have multiple frames or windows. Selenium assigns each window a unique alphanumeric id which is called window handle. Selenium then uses the id to switch control among windows.

⦁ String handle=driver.getWindowHandle();  
Set<String> handles = getWindowHandles();  
driver.switchTo().window(handle);

⦁ How to switch to a newly created window:  
 String curWindow=driver.getWindowHandle();

⦁ Get all window handles:  
 Set<String> handles = getWindowHandles();  
 For(string handle: handles){  
 If (!handle.equals(curWindow))  
 {driver.switchTo().window(handle);  
 }  
 }  
   
Frames:  
⦁ Using Frame Index:  
 driver.switchTO().frame(1);  
⦁ Using Name of Frame:  
 driver.switchTo().frame(“name”)  
⦁ Using web Element Object:  
 driver.switchTO().frame(element);  
⦁ Get back to main document:  
 Select Parent Window  
 driver.switchTO().defaultContent();

  
Operations:  
⦁ Launch Webpage:  
 get("www.webdriverinselenium.com");  
⦁ Click Button:   
 findElement(By.id("submit")).click();  
⦁ Handle Alert:  
 AlertAlertpopup = driver.switchTo().alert();  
⦁ Disable a Field:  
 getElementsByName('') [0].setAttribute('disabled', '')  
⦁ Enable a Field :  
 getElementsByName('') [0].removeAttribute('disabled');  
⦁ Screenshot :   
 File snapshot = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);  
 FileUtils.copyFile(snapshot, new File("C:\\screenshot.jpg"));  
⦁ Print the Title of the Page:  
 String pagetitle = driver.getTitle();  
 System.out.print(pagetitle);  
⦁ Implicit Wait:   
 manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);  
⦁ Explicit Wait:  
 WebDriverWait wait = new WebDriverWait(driver, 20);  
⦁ Sleep :  
 Thread.Sleep(10);

Alerts: Sometimes a message box pops up on the screen to display some kind of notification to the user or maybe an ask for permission or to display a warning etc. These messages are called alerts.  
⦁ Capture the alert message:  
 driver.switchTO().alert.getText();  
⦁ Click on the ‘OK’ button of the alert:  
 driver.switchTO().alert.accept();  
⦁ Click on the ‘Cancel’ button of the alert:  
 driver.switchTO().alert.dismiss();  
⦁ Send some data to the alert box:  
 driver.switchTO().alert.sendKeys(“Text”);

close() and quit() methods:  
a) close(): WebDriver’s close() method closes the web browser window that the user is         currently working on   
               driver.close();

b) quit(): Unlike close() method, quit() method closes down all the windows that the        program has opened.  
  driver.quit();

  
#1) get(): Command using get() to open a URL in the current browser.  
driver.get("https://www.softwaretestinghelp.com");

2) getCurrentUrl(): Command using getCurrentUrl() to check if the URL is correct.  
driver.getCurrentUrl();  
Assert.assertEquals(expectedUrl,  driver.getCurrentUrl());

3) findElement(By, by) and click(): This method is usually used in commands to simulate user                       actions like click, submit, type etc.  
The element can be located using ID, Name, Class Name, Tag Name, Link Text & Partial Link Text, CSS Selector and X Path.  
⦁               driver.findElement(By.id("submit1")).click();  
⦁  WebElement roleDropdown = driver.findElement(By.id("name1");  
               roleDropdown.click();

4) isEnabled(): isEnabled() to Check Whether the Element is Enabled Or Disabled in the         Selenium WebDriver.

boolean textBox = driver.findElement(By.xpath("//input[@name='textbox1']")).isEnabled();

5) findElement(By, by) with sendKeys():  
 driver.findElement(By.name("name")).sendkeys("Aaron");

6) findElement(By, by) with getText():  
 String dropDown = driver.findElement(By.tagName("dropdown1")).getText();  
   
7) Submit():   
driver.findElement(By.xpath("//input[@name='comments']")).submit();  
   
8) findElements(By, by):  
List<WebElement> allChoices = dropDown.findElements(By.xpath(".//fruitoption"));

9) findElements(By, by) with size():  
Boolean checkIfElementPresent=  
driver.findElements(By.xpath("//input[@id='checkbox2']")).size()!= 0;

10) pageLoadTimeout(time,unit):  
pageLoadTimeout(time,unit) to set the time for a page to load.

Sometimes due to server issues or network delays, a page might take more than usual time to load. This might throw an error in the program. In order to avoid this, we set a wait time and pageLoadTimeout() is one of such method. This will usually follow a get() command.

driver.manage().timeouts().pageLoadTimeout(500, SECONDS);

11) implicitlyWait():  
implicitlyWait() to set a wait time before searching and locating a web element.

What happens if the Webdriver tries to locate an element before the webpage loads and the element appears? NoSuchElementExeption will be thrown. In order to avoid this, we can add a command to implicitly wait for a certain amount of time before locating the element.

driver.manage().timeouts().implicitlyWait(1000, TimeUnit.SECONDS);

12) untill() and visibilityOfElementLocated():  
untill() from WebdriverWait and visibilityOfElementLocated() from ExpectedConditions to wait explicitly till an element is visible in the webpage.

To handle cases where an element takes too much time to be visible on the software web page applying implicit wait becomes tricky. In this case, we can write a comment to wait until the element appears on the webpage.

WebDriverWait wait = new WebDriverWait(driver, 10);  
WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated  (By.xpath("//input[@id=’name’]")));

13) untill() and alertIsPresent():  
untill() from WebdriverWait and alertIsPresent() from ExpectedConditions to wait explicitly till an alert appears.  
 WebDriverWait wait = new WebDriverWait(driver, 10);  
 WebElement element = wait.until(ExpectedConditions.alertIsPresent());

14) getTitle():  
String title = driver.getTitle();  
System.out.println(title);

15) Select:  
Select class for selecting and deselecting values from the drop-down in Selenium WebDriver.

We often have dropdown related scenarios. Methods from the Select class is used to handle this. We can use selectByVisibleText(),selectByValue() or selectByIndex() according to the scenario.  
 WebElement mySelectedElement = driver.findElement(By.id("select"));  
 Select dropdown= new Select(mySelectedElement);  
 dropdown.selectByVisibleText("Apple");

 WebElement mySelectedElement = driver.findElement(By.id("select"));  
 Select dropdown= new Select(mySelectedElement);  
 listbox.selectByIndex(1);

 WebElement mySelectedElement = driver.findElement(By.id("select"));  
 Select dropdown= new Select(mySelectedElement);  
 Dropdown.deselectByValue("Apple");

 WebElement mySelectedElement = driver.findElement(By.id("select"));  
 Select dropdown= new Select(mySelectedElement);  
 dropdown.deselectByVisibleText("Apple");

 WebElement mySelectedElement = driver.findElement(By.id("select"));  
 Select dropdown= new Select(mySelectedElement);  
 listbox.deselectByIndex(1);

16) navigate():  
driver.navigate().to("https://www.softwaretestinghelp.com");  
driver.navigate().back();  
driver.navigate().forward();

17)  getScreenshotAs():  
File shot = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);  
FileUtils.copyFile(shot, new File("D:\\ shot1.jpg"));

18) moveToElement():   
moveToElement() from the Actions class to simulate mouse hover effect.

Actions actions = new Actions(driver);  
WebElement mouseHover = driver.findElement(By.xpath("//div[@id='mainmenu1']/div"));  
actions.moveToElement(mouseHover);  
actions.perform();

19) dragAndDrop():  
dragAndDrop() from Actions class to drag an element and drop it on another element.

WebElement sourceLocator = driver.findElement(By.xpath("//*[@id='image1']/a"));  
WebElement destinationLocator = driver.findElement(By.xpath("//*[@id='stage']/li"));  
Actions actions=new Actions(driver);  
actions.dragAndDrop(sourceLocator, destinationLocator).build().perform();

  
20) switchTo() and accept(), dismiss() and sendKeys():  
switchTo() and accept(), dismiss() and sendKeys() methods from Alert class to switch to popup alerts and handle them.

 Alert alert = driver.switchTo().alert();  
 alert.sendKeys("This Is Softwaretestinghelp");  
 alert.accept()

  
21) getWindowHandle() and getWindowHandles():  
getWindowHandle() and getWindowHandles() to handle Multiple Windows in Selenium WebDriver.

 String handle= driver.getWindowHandle();  
 Set<String> handle= driver.getWindowHandles();

 for (String handle : driver.getWindowHandles()){  
 driver.switchTo().window(handle);}

22) getConnection(): getConnection() from DriverManager to start Database Connection.

 DriverManager.getConnection(URL, "username", "password" )

23) POI:POI to read from the excel files.

In data driven testing, we often save inputs in excel file and read it. In order to do this in WebDriver, we import POI package and then use the below command.

 Workbook workbook = WorkbookFactory.create(new FileInputStream(file));  
 Sheet sheet = workbook.getSheetAt(0);

24) assertEquals(),assertNotEquals(), assertTrue() and assertFalse():  
Asserts using assertEquals(),assertNotEquals(), assertTrue() and assertFalse() to compare the results.

Assertions are used to compare the expected and actual results. Pass or fail of a test is usually decided from the result of assertions.

Assert.assertEquals(message, “This text”);  
Assert.assertNotEquals(message, “This text”);  
Assert.assertTrue(result<0);  
Assert.assertFalse(result<0);

25) close() and quit()  
close() and quit() to close windows and driver instances.

These commands are used at the end of every automation program.

 driver.close()  
 driver.quit()