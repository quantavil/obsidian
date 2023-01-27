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
boolean isEnabled = element.isEnabled();
boolean isDisplayed = element.isDisplayed();
boolean isSelected = element.isSelected();
WebElement element = driver.findElement(By.id("id"));


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
// Wait for visibility of an element
WebDriverWait wait = new WebDriverWait(driver, 30);
wait.until(ExpectedConditions.visibilityOfAllElementsLocatedBy(
By.xpath("//*[@id='tve_editor']/div[2]/div[2]/div/div")));
```


## Basic browser Operation

```java
// Navigate to a page
driver.navigate().to("http://google.com");
// Get the title of the page
String title = driver.getTitle();
// Get the current URL
String url = driver.getCurrentUrl();
// Get the current page HTML source
String html = driver.getPageSource();
// Used to retrieve the text of the specified web element
driver.getText()
```

