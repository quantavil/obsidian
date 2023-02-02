-   **@BeforeMethod and @AfterMethod** – These annotations run before and after each test method
-   **@BeforeClass and @AfterClass** – These annotations run once before and after the first _@test_ method in a class
-   **@BeforeTest and @AfterTest** – The BeforeTest annotation runs before the _@BeforeClass_ annotation and the AfterTest annotation runs after the _@AfterClass_ annotation
-   **@BeforeSuite and @AfterSuite**– These annotations run before and after any test annotated method in a class respectively. These annotations start the beginning of a test and the end of it, for all the classes in a suite

Talking about the execution order of these annotations, they execute in the below order:

**_@BeforeSuite -> @BeforeTest -> @BeforeClass -> @BeforeMethod -> @Test -> @AfterMethod -> @AfterClass -> @AfterCTest -> @AfterSuite_**

```ad-info
The key point to remember is apart from _@BeforeMethod_ and _@AfterMethod_, all other annotations run only once, whereas the _@BeforeMethod_ and _@AfterMethod_ run post every _@Test_ method.
```