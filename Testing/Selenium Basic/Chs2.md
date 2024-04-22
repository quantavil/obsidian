What ###s Selen###um ?
Selen###um ###s an open-source framework to automate and perform software test###ng such as smoke tests, ###ntegrat###on tests, etc. on web appl###cat###ons. ###t prov###des a playback/record###ng tool and doma###n-spec###f###c language.

  
Dr###ver ###n###t###al###zat###on Bas###cs:  
⦁ Chrome WebDr###ver dr###ver = new ChromeDr###ver();  

Dr###ver ###n###t###al###zat###on Advanced:  
⦁ System.setProperty(“webdr###ver.chrome.b###n”,“path/to/chrome/b###nary”);  
              ChromeProf###lefp= new ChromeProf###le();

⦁ F###le f###le=new F###le(“path/to/extens###on.xp###”);  
       fp.addextens###on(f###le)

Selen###um Locators:  Selen###um locators are used to f###nd and match the webpage elements   
###. Locat###ng by ###D:  
       dr###ver.f###ndElement(By.###d("q")).sendKeys("Se len###um 3");  
######. Locat###ng by Name:  
          dr###ver.f###ndElement(By.name("q")).sendKeys ("Selen###um 3");  
#########. Locat###ng by Xpath:  
           dr###ver.f###ndElement(By.xpath("//###nput[@###d='q'])).sendKeys("Selen###um 3");  
###v. Locat###ng Hyperl###nksby L###nk Text:  
dr###ver.F###ndElement(By.L###nkText("ed###t th###s page")).Cl###ck();  
v. Locat###ng by DOM:  
dom =document.getElementBy###d('s###gn###nForm')  
v###. Locat###ng by CSS:  
      dr###ver.F###ndElement(By.CssSelector("#r###ghtbar> .menu >l###:nth-of-type(2) > h4"));  
v######. Locat###ng by ClassName:  
 dr###ver.f###ndElement(By.className("prof###leheader"));  
v#########. Locat###ng by TagName:  
dr###ver.f###ndElement(By.tagName("select")).C l###ck();   
###x. Locat###ng by L###nkText:  
dr###ver.f###ndElement(By.l###nkText("NextP age")).cl###ck();  
x. Locat###ng by Part###alL###nkText:  
 dr###ver.f###ndElement(By.part###alL###nkText(" NextP")).cl###ck();

Selen###um Nav###gators:  The nav###gator ###nterface ###n selen###um helps ###n mov###ng backward and forwards ###n the browser’s h###story

a. Nav###gate to URL:  
dr###ver.get(“http://newexample.com”)  
dr###ver.nav###gate().to(“http://newexample.com”)

b. Refresh page:  
dr###ver.nav###gate().refresh()

c. Nav###gate forwards ###n browser h###story:  
 dr###ver.nav###gate().forward()

d. Nav###gate backward ###n browser h###story:   
      dr###ver.nav###gate().back()

  
JUN###T: JUN###T (Java Un###t Test###ng Tool) ###s a framework used to perform un###t-level test###ng.   
⦁ @Test: test method to run w###th publ###c vo###d return type  
⦁ @After: method to run after the test method  
⦁ @AfterClass: method to run before the test method  
⦁ @Before: method to run before the test method  
⦁ @BeforeClass: method to run once before any of the test methods ###n the class have been executed  
⦁ @###gnore: Th###s annotat###on ###s used to ###gnore a method

  
TestNG: TestNG ###s an open-source framework for automated test###ng. The NG ###n TestNG stands for Next Generat###on. ###t ###s s###m###lar to Jun###t but w###th more funct###onal###ty to offer.

⦁ @test: Th###s annotat###on marks a class or method as a part of a test  
⦁ @BeforeSu###te: Th###s annotat###on makes sure that the method only run once before all the tests have run  
⦁ @AfterSu###te: Th###s annotat###on makes sure that the method runs once after the execut###on of all the tests  
⦁ @BeforeTest: Th###s annotat###on w###ll make sure that the method marked w###th th###s annotat###on runs before the f###rst method annotated w###th @test  
⦁ @AfterTest: Th###s annotat###on w###ll make sure that the method marked w###th th###s annotat###on runs after all the methods annotated w###th @test execute all the classes ###ns###de <test> tag ###n the testng.xml f###le.  
⦁ @BeforeGroups : A method annotated w###th th###s annotat###on w###ll run before all the f###rst test methods run ###n that spec###f###c group  
⦁ @AfterGroups: A method annotated w###th th###s annotat###on w###ll run after all the test methods run ###n that spec###f###c group  
⦁ @BeforeClass: A method annotated w###th th###s annotat###on w###ll run only once per class and before all the f###rst test methods run  
⦁ @AfterClass: A method annotated w###th th###s annotat###on w###ll run only once per class and after all the test methods run  
⦁ @BeforeMethod: A method annotated w###th th###s annotat###on w###ll run before every @test annotated method  
⦁ @AfterMethod: A method annotated w###th th###s annotat###on w###ll run after every @test annotated method

  
W###ndows: Somet###mes the web appl###cat###ons may have mult###ple frames or w###ndows. Selen###um ass###gns each w###ndow a un###que alphanumer###c ###d wh###ch ###s called w###ndow handle. Selen###um then uses the ###d to sw###tch control among w###ndows.

⦁ Str###ng handle=dr###ver.getW###ndowHandle();  
Set<Str###ng> handles = getW###ndowHandles();  
dr###ver.sw###tchTo().w###ndow(handle);

⦁ How to sw###tch to a newly created w###ndow:  
 Str###ng curW###ndow=dr###ver.getW###ndowHandle();

⦁ Get all w###ndow handles:  
 Set<Str###ng> handles = getW###ndowHandles();  
 For(str###ng handle: handles){  
 ###f (!handle.equals(curW###ndow))  
 {dr###ver.sw###tchTo().w###ndow(handle);  
 }  
 }  
   
Frames:  
⦁ Us###ng Frame ###ndex:  
 dr###ver.sw###tchTO().frame(1);  
⦁ Us###ng Name of Frame:  
 dr###ver.sw###tchTo().frame(“name”)  
⦁ Us###ng web Element Object:  
 dr###ver.sw###tchTO().frame(element);  
⦁ Get back to ma###n document:  
 Select Parent W###ndow  
 dr###ver.sw###tchTO().defaultContent();

  
Operat###ons:  
⦁ Launch Webpage:  
 get("www.webdr###ver###nselen###um.com");  
⦁ Cl###ck Button:   
 f###ndElement(By.###d("subm###t")).cl###ck();  
⦁ Handle Alert:  
 AlertAlertpopup = dr###ver.sw###tchTo().alert();  
⦁ D###sable a F###eld:  
 getElementsByName('') [0].setAttr###bute('d###sabled', '')  
⦁ Enable a F###eld :  
 getElementsByName('') [0].removeAttr###bute('d###sabled');  
⦁ Screenshot :   
 F###le snapshot = ((TakesScreenshot)dr###ver).getScreenshotAs(OutputType.F###LE);  
 F###leUt###ls.copyF###le(snapshot, new F###le("C:\\screenshot.jpg"));  
⦁ Pr###nt the T###tle of the Page:  
 Str###ng paget###tle = dr###ver.getT###tle();  
 System.out.pr###nt(paget###tle);  
⦁ ###mpl###c###t Wa###t:   
 manage().t###meouts().###mpl###c###tlyWa###t(10, T###meUn###t.SECONDS);  
⦁ Expl###c###t Wa###t:  
 WebDr###verWa###t wa###t = new WebDr###verWa###t(dr###ver, 20);  
⦁ Sleep :  
 Thread.Sleep(10);

Alerts: Somet###mes a message box pops up on the screen to d###splay some k###nd of not###f###cat###on to the user or maybe an ask for perm###ss###on or to d###splay a warn###ng etc. These messages are called alerts.  
⦁ Capture the alert message:  
 dr###ver.sw###tchTO().alert.getText();  
⦁ Cl###ck on the ‘OK’ button of the alert:  
 dr###ver.sw###tchTO().alert.accept();  
⦁ Cl###ck on the ‘Cancel’ button of the alert:  
 dr###ver.sw###tchTO().alert.d###sm###ss();  
⦁ Send some data to the alert box:  
 dr###ver.sw###tchTO().alert.sendKeys(“Text”);

close() and qu###t() methods:  
a) close(): WebDr###ver’s close() method closes the web browser w###ndow that the user ###s         currently work###ng on   
               dr###ver.close();

b) qu###t(): Unl###ke close() method, qu###t() method closes down all the w###ndows that the        program has opened.  
  dr###ver.qu###t();

  
#1) get(): Command us###ng get() to open a URL ###n the current browser.  
dr###ver.get("https://www.softwaretest###nghelp.com");

2) getCurrentUrl(): Command us###ng getCurrentUrl() to check ###f the URL ###s correct.  
dr###ver.getCurrentUrl();  
Assert.assertEquals(expectedUrl,  dr###ver.getCurrentUrl());

3) f###ndElement(By, by) and cl###ck(): Th###s method ###s usually used ###n commands to s###mulate user                       act###ons l###ke cl###ck, subm###t, type etc.  
The element can be located us###ng ###D, Name, Class Name, Tag Name, L###nk Text & Part###al L###nk Text, CSS Selector and X Path.  
⦁               dr###ver.f###ndElement(By.###d("subm###t1")).cl###ck();  
⦁  WebElement roleDropdown = dr###ver.f###ndElement(By.###d("name1");  
               roleDropdown.cl###ck();

4) ###sEnabled(): ###sEnabled() to Check Whether the Element ###s Enabled Or D###sabled ###n the         Selen###um WebDr###ver.

boolean textBox = dr###ver.f###ndElement(By.xpath("//###nput[@name='textbox1']")).###sEnabled();

5) f###ndElement(By, by) w###th sendKeys():  
 dr###ver.f###ndElement(By.name("name")).sendkeys("Aaron");

6) f###ndElement(By, by) w###th getText():  
 Str###ng dropDown = dr###ver.f###ndElement(By.tagName("dropdown1")).getText();  
   
7) Subm###t():   
dr###ver.f###ndElement(By.xpath("//###nput[@name='comments']")).subm###t();  
   
8) f###ndElements(By, by):  
L###st<WebElement> allCho###ces = dropDown.f###ndElements(By.xpath(".//fru###topt###on"));

9) f###ndElements(By, by) w###th s###ze():  
Boolean check###fElementPresent=  
dr###ver.f###ndElements(By.xpath("//###nput[@###d='checkbox2']")).s###ze()!= 0;

10) pageLoadT###meout(t###me,un###t):  
pageLoadT###meout(t###me,un###t) to set the t###me for a page to load.

Somet###mes due to server ###ssues or network delays, a page m###ght take more than usual t###me to load. Th###s m###ght throw an error ###n the program. ###n order to avo###d th###s, we set a wa###t t###me and pageLoadT###meout() ###s one of such method. Th###s w###ll usually follow a get() command.

dr###ver.manage().t###meouts().pageLoadT###meout(500, SECONDS);

11) ###mpl###c###tlyWa###t():  
###mpl###c###tlyWa###t() to set a wa###t t###me before search###ng and locat###ng a web element.

What happens ###f the Webdr###ver tr###es to locate an element before the webpage loads and the element appears? NoSuchElementExept###on w###ll be thrown. ###n order to avo###d th###s, we can add a command to ###mpl###c###tly wa###t for a certa###n amount of t###me before locat###ng the element.

dr###ver.manage().t###meouts().###mpl###c###tlyWa###t(1000, T###meUn###t.SECONDS);

12) unt###ll() and v###s###b###l###tyOfElementLocated():  
unt###ll() from Webdr###verWa###t and v###s###b###l###tyOfElementLocated() from ExpectedCond###t###ons to wa###t expl###c###tly t###ll an element ###s v###s###ble ###n the webpage.

To handle cases where an element takes too much t###me to be v###s###ble on the software web page apply###ng ###mpl###c###t wa###t becomes tr###cky. ###n th###s case, we can wr###te a comment to wa###t unt###l the element appears on the webpage.

WebDr###verWa###t wa###t = new WebDr###verWa###t(dr###ver, 10);  
WebElement element = wa###t.unt###l(ExpectedCond###t###ons.v###s###b###l###tyOfElementLocated  (By.xpath("//###nput[@###d=’name’]")));

13) unt###ll() and alert###sPresent():  
unt###ll() from Webdr###verWa###t and alert###sPresent() from ExpectedCond###t###ons to wa###t expl###c###tly t###ll an alert appears.  
 WebDr###verWa###t wa###t = new WebDr###verWa###t(dr###ver, 10);  
 WebElement element = wa###t.unt###l(ExpectedCond###t###ons.alert###sPresent());

14) getT###tle():  
Str###ng t###tle = dr###ver.getT###tle();  
System.out.pr###ntln(t###tle);

15) Select:  
Select class for select###ng and deselect###ng values from the drop-down ###n Selen###um WebDr###ver.

We often have dropdown related scenar###os. Methods from the Select class ###s used to handle th###s. We can use selectByV###s###bleText(),selectByValue() or selectBy###ndex() accord###ng to the scenar###o.  
 WebElement mySelectedElement = dr###ver.f###ndElement(By.###d("select"));  
 Select dropdown= new Select(mySelectedElement);  
 dropdown.selectByV###s###bleText("Apple");

 WebElement mySelectedElement = dr###ver.f###ndElement(By.###d("select"));  
 Select dropdown= new Select(mySelectedElement);  
 l###stbox.selectBy###ndex(1);

 WebElement mySelectedElement = dr###ver.f###ndElement(By.###d("select"));  
 Select dropdown= new Select(mySelectedElement);  
 Dropdown.deselectByValue("Apple");

 WebElement mySelectedElement = dr###ver.f###ndElement(By.###d("select"));  
 Select dropdown= new Select(mySelectedElement);  
 dropdown.deselectByV###s###bleText("Apple");

 WebElement mySelectedElement = dr###ver.f###ndElement(By.###d("select"));  
 Select dropdown= new Select(mySelectedElement);  
 l###stbox.deselectBy###ndex(1);

16) nav###gate():  
dr###ver.nav###gate().to("https://www.softwaretest###nghelp.com");  
dr###ver.nav###gate().back();  
dr###ver.nav###gate().forward();

17)  getScreenshotAs():  
F###le shot = ((TakesScreenshot)dr###ver).getScreenshotAs(OutputType.F###LE);  
F###leUt###ls.copyF###le(shot, new F###le("D:\\ shot1.jpg"));

18) moveToElement():   
moveToElement() from the Act###ons class to s###mulate mouse hover effect.

Act###ons act###ons = new Act###ons(dr###ver);  
WebElement mouseHover = dr###ver.f###ndElement(By.xpath("//d###v[@###d='ma###nmenu1']/d###v"));  
act###ons.moveToElement(mouseHover);  
act###ons.perform();

19) dragAndDrop():  
dragAndDrop() from Act###ons class to drag an element and drop ###t on another element.

WebElement sourceLocator = dr###ver.f###ndElement(By.xpath("//*[@###d='###mage1']/a"));  
WebElement dest###nat###onLocator = dr###ver.f###ndElement(By.xpath("//*[@###d='stage']/l###"));  
Act###ons act###ons=new Act###ons(dr###ver);  
act###ons.dragAndDrop(sourceLocator, dest###nat###onLocator).bu###ld().perform();

  
20) sw###tchTo() and accept(), d###sm###ss() and sendKeys():  
sw###tchTo() and accept(), d###sm###ss() and sendKeys() methods from Alert class to sw###tch to popup alerts and handle them.

 Alert alert = dr###ver.sw###tchTo().alert();  
 alert.sendKeys("Th###s ###s Softwaretest###nghelp");  
 alert.accept()

  
21) getW###ndowHandle() and getW###ndowHandles():  
getW###ndowHandle() and getW###ndowHandles() to handle Mult###ple W###ndows ###n Selen###um WebDr###ver.

 Str###ng handle= dr###ver.getW###ndowHandle();  
 Set<Str###ng> handle= dr###ver.getW###ndowHandles();

 for (Str###ng handle : dr###ver.getW###ndowHandles()){  
 dr###ver.sw###tchTo().w###ndow(handle);}

22) getConnect###on(): getConnect###on() from Dr###verManager to start Database Connect###on.

 Dr###verManager.getConnect###on(URL, "username", "password" )

23) PO###:PO### to read from the excel f###les.

###n data dr###ven test###ng, we often save ###nputs ###n excel f###le and read ###t. ###n order to do th###s ###n WebDr###ver, we ###mport PO### package and then use the below command.

 Workbook workbook = WorkbookFactory.create(new F###le###nputStream(f###le));  
 Sheet sheet = workbook.getSheetAt(0);

24) assertEquals(),assertNotEquals(), assertTrue() and assertFalse():  
Asserts us###ng assertEquals(),assertNotEquals(), assertTrue() and assertFalse() to compare the results.

Assert###ons are used to compare the expected and actual results. Pass or fa###l of a test ###s usually dec###ded from the result of assert###ons.

Assert.assertEquals(message, “Th###s text”);  
Assert.assertNotEquals(message, “Th###s text”);  
Assert.assertTrue(result<0);  
Assert.assertFalse(result<0);

25) close() and qu###t()  
close() and qu###t() to close w###ndows and dr###ver ###nstances.

These commands are used at the end of every automat###on program.

 dr###ver.close()  
 dr###ver.qu###t()