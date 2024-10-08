## Driver Initialization

```java
// Maven: selenium-chrome-driver
import org.openqa.selenium.chrome.ChromeDriver;
WebDriver driver = new ChromeDriver();
// Maven: selenium-firefox-driver
import org.openqa.selenium.firefox.FirefoxDriver;
WebDriver driver = new FirefoxDriver();
// Maven: selenium-edge-driver
import org.openqa.selenium.firefox.EdgeDriver;
WebDriver driver = new EdgeDriver();
```

## Browser Initialization

-  **Firefox**

`WebDriver driver = new FirefoxDriver();`
  
-  **Chrome**

`WebDriver driver = new ChromeDriver();`

## Locator

```java
driver.findElement(By.className("className"));
driver.findElement(By.cssSelector("css"));
driver.findElement(By.id("id"));
driver.findElement(By.linkText("text"));
driver.findElement(By.name("name"));
driver.findElement(By.partialLinkText("pText"));
driver.findElement(By.tagName("input"));
driver.findElement(By.xpath("//*[@id='editor']"));
// Find multiple elements
List<WebElement> anchors = driver.findElements(By.tagName("a"));
// Search for an element inside another
WebElement div = driver.findElement(By.tagName("div"))
 .findElement(By.tagName("a"));
```

## Basic Elements Operations
```java

WebElement element = driver.findElement(By.id("id"));
element.click(); // method is used to click on en element
element.sendKeys("someText"); // method is used to send data
element.clear(); //method is used to clear text from text area
element.submit();
String innerText = element.getText();
WebElement element = driver.findElement(By.id("id"));

// Element validation
boolean isEnabled = element.isEnabled();
boolean isDisplayed = element.isDisplayed();
boolean isSelected = element.isSelected();



//## Selecting Single Option from Drop Down
Select select = new Select(element);
select.selectByIndex(1);
select.selectByVisibleText("Ford");
select.selectByValue("ford");
select.deselectAll();
select.deselectByIndex(1);
select.deselectByVisibleText("Ford");
select.deselectByValue("ford");
List<WebElement> allSelected = select.getAllSelectedOptions();
boolean isMultipleSelect = select.isMultiple();
```

## Advance Elements Operations

```java
// Drag and Drop
WebElement element = driver.FindElement(
By.xpath("//*[@id='project']/p[1]/div/div[2]"));
Actions move = new Actions(driver);
action.dragAndDrop(Sourcelocator, Destinationlocator).build().perform();
move.dragAndDropBy(element, 30, 0).build().perform();

// How to check if an element is visible
Assert.assertTrue(driver.findElement(
By.xpath("//*[@id='tve_editor']/div")).isDisplayed());

// Upload a file
WebElement element = driver.findElement(By.id("RadUpload1file0"));
String filePath = "D:WebDriver.Series.TestsWebDriver.xml";
element.sendKeys(filePath);

// Scroll focus to control
WebElement link =
driver.findElement(By.partialLinkText("Previous post"));
String js = String.format("window.scroll(0, %d);",
link.getLocation().getY());
((JavascriptExecutor)driver).executeScript(js);
link.click();

// Taking an element screenshot
WebElement element =
driver.findElement(By.xpath("//*[@id='tve_editor']/div"));
File screenshotFile =
((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
BufferedImage fullImg = ImageIO.read(screenshotFile);
Point point = element.getLocation();
int elementWidth = element.getSize().getWidth();
int elementHeight = element.getSize().getHeight();
BufferedImage eleScreenshot = fullImg.getSubimage(point.getX(), point.getY(), elementWidth, elementHeight);
ImageIO.write(eleScreenshot, "png", screenshotFile);
String tempDir = getProperty("java.io.tmpdir");
File destFile = new File(Paths.get(tempDir, fileName + ".png").toString());
FileUtils.getFileUtils().copyFile(screenshotFile, destFile);

// Focus on a control
WebElement link =
driver.findElement(By.partialLinkText("Previous post"));
Actions action = new Actions(driver);
action.moveToElement(link).build().perform();

```


## Wait 

- **Implicit Wait**—used to wait for a certain amount of time before throwing an exception

```java
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
```

-  **Explicit Wait** — used to wait until a certain condition occurs before executing the code

```java
WebDriverWait wait = new WebDriverWait(driver,30);
wait.until(ExpectedConditions.presenceOfElementLocated(By.name("login")));

// List of explicit Wait
alertIsPresent()
elementSelectionStateToBe()
elementToBeClickable()
elementToBeSelected()
frameToBeAvaliableAndSwitchToIt()
invisibilityOfTheElementLocated()
invisibilityOfElementWithText()
presenceOfAllElementsLocatedBy()
presenceOfElementLocated()
textToBePresentInElement()
textToBePresentInElementLocated()
textToBePresentInElementValue()
titleIs()
titleContains()
visibilityOf()
visibilityOfAllElements()
visibilityOfAllElementsLocatedBy()
visibilityOfElementLocated()
```

- **Fluent Wait** — defines the maximum amount of time to wait for a certain condition to appear
```java
Wait wait = new FluentWait(WebDriver reference)
.withTimeout(Duration.ofSeconds(SECONDS))
.pollingEvery(Duration.ofSeconds(SECONDS))
.ignoring(Exception.class);

WebElement foo=wait.until(new Function<WebDriver, WebElement>() {
public WebElement apply(WebDriver driver) {
return driver.findElement(By.id("foo"));
}
});

```


## Basic browser Operation

```java
// Navigate to a page
driver.navigate().to("http://google.com");

// Navigation history
driver.navigate().back();
driver.navigate().refresh();
driver.navigate().forward();


// Get the title of the page
String title = driver.getTitle();
// Get the current URL
String url = driver.getCurrentUrl();
// Get the current page HTML source
String html = driver.getPageSource();
// Used to retrieve the text of the specified web element
driver.getText();
// method is declared in the WebElement interface, and it returns the value of the web element’s attribute as a string
driver.getAttribute();
```


```ad-info
**`driver.get()` :** It's used to go to the particular website , But it doesn't maintain the browser History and cookies so , we can't use forward and backward button , if we click on that , page will not get schedule

**`driver.navigate()` :** it's used to go to the particular website , but it maintains the browser history and cookies, so we can use forward and backward button to navigate between the pages during the coding of Testcase
```


## Advance browser Operation

```java
// Handle JavaScript pop-ups
Alert alert = driver.switchTo().alert();
alert.accept();
alert.dismiss();
driver.switchTO().alert.getText()
driver.switchTO().alert.sendKeys(“Text”)

// Maximize window
driver.manage().window().maximize();

// Switch between browser windows or tabs
Set<String> windowHandles = driver.getWindowHandles();
String firstTab = (String)windowHandles.toArray()[1];
String lastTab = (String)windowHandles.toArray()[2];
driver.switchTo().window(lastTab);

//  closes the current browser window
driver.close()

// Switch to frames
driver.switchTo().frame(1);
driver.switchTo().frame("frameName");
WebElement element = driver.findElement(By.id("id"));
driver.switchTo().frame(element);
driver.switchTo().defaultContent();  //# Switching to default content

// Add a new cookie
Cookie newCookie = new Cookie("customName", "customValue");
driver.manage().addCookie(newCookie);

// Get all cookies
Set<Cookie> cookies = driver.manage().getCookies();

// Delete a cookie by name
driver.manage().deleteCookieNamed("CookieName");

// Delete all cookies
driver.manage().deleteAllCookies();

//Taking a full-screen screenshot
File srceenshotFile = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
String tempDir = getProperty("java.io.tmpdir");
File destFile = new File(Paths.get(tempDir, fileName + ".png").toString());
FileUtils.getFileUtils().copyFile(srceenshotFile, destFile);
// Wait until a page is fully loaded via JavaScript
WebDriverWait wait = new WebDriverWait(driver, 30);
wait.until(x -> {
 ((String)((JavascriptExecutor)driver).executeScript(
 "return document.readyState")).equals("complete");
});



```

---
---


```java

// Selenium
package Plasma;

import static org.junit.Assert.assertEquals;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.List;
import java.util.concurrent.TimeUnit;

import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.Assert;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;

public class Test1 {
    WebDriver driver;

    @BeforeClass
    public void before() throws Exception {
        System.setProperty("webdriver.chrome.driver",
                "C:\\Users\\karan.rawat01\\Downloads\\chromedriver_win32 (1)\\chromedriver.exe");
        driver = new ChromeDriver();
        driver.get("http://10.82.181.42/Automation/HMS/LoginPage.aspx");
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(8, TimeUnit.SECONDS);
    }

    @DataProvider(name = "login_cred")
    public static Object[][] getData() {
        Object[][] data = new Object[1][2];
        data[0][0] = "127";
        data[0][1] = "admin";
        return data;
    }

    @Test(dataProvider = "login_cred")
    public void test1(String usrId, String pass) throws Exception {

        driver.findElement(By.id("txtUserID")).sendKeys(usrId);
        driver.findElement(By.id("txtPassword")).sendKeys(pass);
        driver.findElement(By.name("btnLogin")).click();
        Thread.sleep(1200, 0);

        String wel = driver.findElement(By.id("lblLoginUser")).getText();

        Assert.assertEquals(wel, "Hi, John Paul");
        System.out.println("Truw");
    }

        int k = 1;
        do {
            k = k + 1;
            Thread.sleep(1400, k);
            WebElement table = driver
                    .findElement(By.xpath("//*[@id=\"cphMainContent_tcBloodDonor_tpViewDonor_gvViewDonors\"]/tbody"));
            List<WebElement> rows = table.findElements(By.tagName("tr"));

            for (int i = 1; i < rows.size(); i++) {
                List<WebElement> cols = rows.get(i).findElements(By.tagName("td"));
                if (cols.get(3).getText().equalsIgnoreCase("Female")) {
                    System.out.println(cols.get(7).getText());

                }
            }
            driver.findElement(By.linkText(Integer.toString(k))).click();

        } while (k < 3);
    }

    @Test(priority = 3)
    public void test3() throws Exception {
        driver.findElement(By.id("__tab_cphMainContent_tcBloodDonor_tpUpdateDonor")).click();
        ;
        Thread.sleep(1800, 0);
        driver.findElement(By.id("cphMainContent_tcBloodDonor_tpUpdateDonor_rblConditions_0")).click();
        Thread.sleep(1200, 0);
        driver.findElement(By.id("cphMainContent_tcBloodDonor_tpUpdateDonor_rblStatus_0")).click();
        Thread.sleep(1500, 0);
        driver.findElement(By
                .xpath("//*[@id=\"cphMainContent_tcBloodDonor_tpUpdateDonor_gvUpdateDonor\"]/tbody/tr[2]/td[9]/input"))
                .click();
        driver.findElement(By.id("cphMainContent_tcBloodDonor_tpUpdateDonor_txtAddressU"))
                .sendKeys("15th Avenue Street ,New York");
        driver.findElement(By.name("ctl00$cphMainContent$tcBloodDonor$tpUpdateDonor$btnUpdateDonor")).click();

        WebDriverWait wait = new WebDriverWait(driver, 30);
        wait.until(ExpectedConditions
                .visibilityOfElementLocated(By.id("cphMainContent_tcBloodDonor_tpUpdateDonor_lblMessagesUpdate")));

        String actual = driver.findElement(By.id("cphMainContent_tcBloodDonor_tpUpdateDonor_lblMessagesUpdate"))
                .getText();
        assertEquals("Data updated successfully", actual);

    }

    @Test(priority = 2)
    public void test4() throws Exception {
        FileInputStream fis = new FileInputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Plasma\\BloodDonors.xlsx");
        XSSFWorkbook workbook = new XSSFWorkbook(fis);
        XSSFSheet sheet = workbook.getSheet("Sheet1");

        int noOfRows = sheet.getLastRowNum() - sheet.getFirstRowNum();
        driver.findElement(By.id("__tab_cphMainContent_tcBloodDonor_tpAddDonor")).click();

        for (int i = 1; i <= noOfRows; i++) {
            String fName = sheet.getRow(i).getCell(0).getStringCellValue();
            String lName = 

            driver.findElement(By.name("ctl00$cphMainContent$tcBloodDonor$tpAddDonor$btnResetAdd")).click();
            Thread.sleep(1800, 0);

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtDonorFirstName")).sendKeys(fName);
            

            WebElement bloodG = driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_ddlBloodGroup"));
            Select op = new Select(bloodG);
            op.selectByVisibleText(blood);
        }

        FileOutputStream fos = new FileOutputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Plasma\\BloodDonors.xlsx");
        workbook.write(fos);
        workbook.close();
        fos.close();
    }

}
```


```java
package Plasma;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.List;

import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Prob1 {

    WebDriver driver;

    @Before
    public void before() throws Exception {
        System.setProperty("webdriver.chrome.driver",
                "C:\\Users\\karan.rawat01\\Downloads\\chromedriver_win32 (1)\\chromedriver.exe");
        driver = new ChromeDriver();
        driver.get("https://kworb.net/spotify/artists.html");
        driver.manage().window().maximize();
    }

    @Test
    public void test() throws Exception {

        FileInputStream fis = new FileInputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Plasma\\music.xlsx");

        XSSFWorkbook workbook = new XSSFWorkbook(fis);
        XSSFSheet sheet = workbook.getSheet("Sheet1");

        WebElement table = driver.findElement(By.id("spotifyartistindex"));
        List<WebElement> rows = table.findElements(By.tagName("tr"));

        for (int i = 1; i < 2001; i++) {
            List<WebElement> cols = rows.get(i).findElements(By.tagName("td"));
            // for (int j = 0; j < cols.size(); j++) {
            //     System.out.print(cols.get(j).getText() + " , ");
            // }
            List<WebElement> cell = cols.get(1).findElements(By.tagName("a"));
            System.out.print(cols.get(1).getText());
            // System.out.println(cell.get(0).getAttribute("href"));
            
            sheet.createRow(i).createCell(0).setCellValue(cols.get(1).getText());
            sheet.getRow(i).createCell(1).setCellValue(cell.get(0).getAttribute("href"));

        }

        
        FileOutputStream fos = new FileOutputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Plasma\\music.xlsx");
        workbook.write(fos);
        workbook.close();
        fos.close();
    }
}

```


---
---

## TestNG
```java

// testng
package ab_testng;

import org.testng.annotations.AfterClass;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.AfterSuite;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.BeforeSuite;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class Demo1 {
	@BeforeMethod
	public void beforeMethod() {
		System.out.println("Demo1-BeforeMethod");
	}

	@Test (groups = {"sanity", "regression"})
	public void test1() {
		System.out.println("Demo1-Test case 1");
	}

	@BeforeTest
	public void beforeTest() { // run before any test method - xml<test> before
		System.out.println("Demo1-Before Test");
	}

	@AfterTest
	public void afterTest() { // run after any test method - xml<test> after
		System.out.println("Demo1-After Test");
	}

	@BeforeClass
	public void beforeClass() {
		System.out.println("Demo1 - Before Class");
	}

	@AfterClass
	public void afterClass() {
		System.out.println("Demo 1 - After Class");
	}

	@Test(priority = 1, groups = {"sanity"})
	public void test2() {
		System.out.println("Demo 1 ##- Test Case 2");
	}
	@Test(priority = 3, dependsOnMethods = {"test4","test1"},alwaysRun = true)
	public void test3() {
		System.out.println("Demo 1 ###- Test Case 3");
	}
	@Test(priority = 2, enabled = true, groups = {"regression"})
	public void test4() {
		System.out.println("Demo 1 ####- Test Case 4");
	}

	@BeforeSuite // method run before all tests in this suite
	public void beforeSuite() {
		System.out.println("Demo1- Before Suite");
	}

	@AfterSuite // method run after all tests in this suite
	public void afterSuite() {
		System.out.println("Demo1 - After Suite");
	}

	@AfterMethod
	public void afterMethod() {
		System.out.println("Demo1 - After Method");
	}
}

```

```java
// testng
package ab_testng;


import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;

public class Demo2 {
	WebDriver driver;
	String expected = "http://10.82.180.36/Accounts/Customer/CustomerAccountHome.aspx";

	@BeforeClass
	public void beforeClass() {
		System.setProperty("webdriver.chrome.driver",
				"C:\\Users\\karan.rawat01\\Documents\\chromedriver110\\chromedriver.exe");
		driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
		driver.get("http://10.82.180.36/Common/Login.aspx");
	}

	@Test
	public void test1() throws Exception {
		driver.findElement(By.id("body_txtUserID")).sendKeys("donhere");
		driver.findElement(By.id("body_txtPassword")).sendKeys("don@123");
		driver.findElement(By.id("body_btnLogin")).click();
		
		String actual = driver.getCurrentUrl();
		
		Assert.assertEquals(expected, actual );
		Assert.assertTrue(driver.findElement(By.id("body_cph_MyAccount_header_divHeader")).isDisplayed());
		driver.findElement(By.linkText("Add Payee")).click();
		Thread.sleep(4000);
	}
	
	@Test
	public void test2() throws Exception {
		System.out.println("out2");
	}
	
	@AfterClass
	public void afterClass() {
//		driver.quit();
	}

}

```


```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite name="Suite">
	<test name="Test">

		<groups>
			<run>
				<include name="sanity" />
				<exclude name="regression" />

			</run>
		</groups>
		<classes>
			<class name="ab_testng.Demo1">
				<methods>
					<include name="beforeSuite" />
				</methods>
			</class>

			<class name="ab_testng.Demo2">
				<methods>
					<exclude name="test2" />
				</methods>
			</class>
		</classes>
	</test> <!-- Test -->
</suite> <!-- Suite -->

```

---

```java

package ab_testng;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.testng.Assert;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Optional;
import org.testng.annotations.Parameters;
import org.testng.annotations.Test;

public class Demo3 {
	WebDriver driver;
	String expected = "http://10.82.180.36/Accounts/Customer/CustomerAccountHome.aspx";

	@BeforeMethod
	@Parameters({ "browser", "url" })
	public void beforeMethod(@Optional("chrome") String browser, String url) {
		if (browser.equalsIgnoreCase("chrome")) {
			System.setProperty("webdriver.chrome.driver",
					"C:\\Users\\karan.rawat01\\Documents\\chromedriver110\\chromedriver.exe");
			driver = new ChromeDriver();
			driver.manage().window().maximize();
			driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
			driver.get(url);

		} else {

			System.setProperty("webdriver.gecko.driver",
					"C:\\Users\\karan.rawat01\\Documents\\geckodriver32\\geckodriver.exe");
			driver = new FirefoxDriver();
			driver.manage().window().maximize();
			driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
			driver.get(url);

		}
	}

	@Test(dataProvider = "login_cred")
	public void test(String arg1 , String arg2) {
		driver.findElement(By.id("body_txtUserID")).sendKeys(arg1);
		driver.findElement(By.id("body_txtPassword")).sendKeys(arg2);
		driver.findElement(By.id("body_btnLogin")).click();
		String actual = driver.getCurrentUrl();
		Assert.assertEquals(expected, actual);
	}
	
    @DataProvider(name = "login_cred")
    public static Object[][] getData() {
//    	Object[][] data = {{"donhere","don123"},{"donhere","don@123"}};
        Object[][] data = new Object[1][2];
        data[0][0] = "donhere";
        data[0][1] = "don@123";
        return data;
    }

	@AfterMethod
	public void afterMethod() {
		driver.quit();
	}

}

```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite name="Suite">

	<parameter name="browser" value="chrome" />
	<parameter name="url" 
		value="http://10.82.180.36/Common/Login.aspx" />
	<test name="Test1">
		<classes>
			<class name="ab_testng.Demo3" />
		</classes>
	</test> <!-- Test -->
	
	<parameter name="browser" value="firefox" />
	<parameter name="url"
		value="http://10.82.180.36/Common/Login.aspx" />
	<test name="Test2">
		<classes>
			<class name="ab_testng.Demo3" />
		</classes>
	</test> <!-- Test -->
</suite> <!-- Suite -->

```


---
---

## Cucumber

```Gherkin
Feature: Test the background feature in AUT
  
 Background: 
  Given User is on EDU Teller Login Page 
  Scenario: 
    When User checks for Add Money
    Then Enter Account number details and Search
    And Closes 
  Scenario: User checks for My Customers
    When The user checks for My Customers link 
    Then All Customer details displayed
    And Closes The Browser
```

```Gherkin
Feature: INEssence Bank Test

  Background: To Test the SignUp/Forgot password Functionality
    Given Open In Essence Bank Site

  Scenario: To check signup functionality in IEB application
    When click on signup in IEB application
    Then Inspect the signup page of IEB application
    And close the browser

  Scenario: To check forgot password IEB application
    When click on forgot password in IEB application
    Then Inspect the forgot password page of IEB application
    And close the browser

```

```Gherkin
# 1. Parameterization using simple data values
# In this technique, you type the data value directly in the scenario. 
# In the below test case, 'ABCD' is considered as a direct data value.
Feature: Testing simple parameterization
Scenario: Login functionality
Given open the browser and url for parameterization
When enter username "donhere" and password "don@123"
Then click on login
```

```Gherkin
Feature: Login Action

  Scenario: Successful Login with valid credentials
    Given user is on homepage
    When user navigate to login page Enter
    And user enter the login credentials
      | Username  | Password  |
      | pgAlmacho | freezeray |
      | pgGru     | freezeray |
    Then Message displayed DASHBOARD

```

```java

	@When("^user enter the login credentials$")
	public void user_enter_the_login_credentials(DataTable arg1) throws Throwable {
		for (Map<String, String> data : arg1.asMaps(String.class, String.class)) {

}

```

```Gherkin
Feature: Testing Scenario Outline

  Scenario Outline: Testing login behaviour
    Given open the browser enter the url so
    When enter user "<username>" and pass "<password>"
    Then click on login in
  
    Examples: 
      | username | password |
      | donhere  | don@123  |
      | user1    | pass1    |
      | user2    | pass2    |

```

```Gherkin

Feature: Tags in Feature FIle
  @EDUBankCustomer
  Scenario: Open AUT and Print Title
    Given The Customer is on Edu login Page
    When Inspect web page
    Then quit browser
    
  @EDUBankTeller
  Scenario: Open AUT and Print Title
    Given EDU Bank Teller Home Page
    When Inspect web page
    Then quit browser
   

```

```Gherkin
Feature: Login Action, Search for buses
	@sanity
	Scenario: Successful Login with Valid Credentials
		Given User is on Travel Home Page

	@regression
	Scenario: Search for the buses
		When user selects the from and to City

	@sanity @regression
	Scenario: Successful LogOut
		Then user click on logout
```