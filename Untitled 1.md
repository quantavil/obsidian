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

  

    @Test(priority = 1)

    public void test2() throws Exception {

  

        driver.findElement(By.id("LinkButton2")).click();

        driver.findElement(By.linkText("Donors")).click();

        driver.findElement(By.id("__tab_cphMainContent_tcBloodDonor_tpViewDonor")).click();

        driver.findElement(By.id("cphMainContent_tcBloodDonor_tpViewDonor_rblConditions1_1")).click();

  

        Thread.sleep(900);

  

        WebElement blood = driver.findElement(By.id("cphMainContent_tcBloodDonor_tpViewDonor_ddlBloodGroupV"));

        Select type = new Select(blood);

        type.selectByVisibleText("A1B+");

        Thread.sleep(900);

  

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

            String lName = sheet.getRow(i).getCell(1).getStringCellValue();

            String address = sheet.getRow(i).getCell(2).getStringCellValue();

            String contact = sheet.getRow(i).getCell(3).getRawValue();

            String email = sheet.getRow(i).getCell(4).getStringCellValue();

            String blood = sheet.getRow(i).getCell(5).getStringCellValue();

            String gender = sheet.getRow(i).getCell(6).getStringCellValue();

            String date = sheet.getRow(i).getCell(7).getStringCellValue();

  

            driver.findElement(By.name("ctl00$cphMainContent$tcBloodDonor$tpAddDonor$btnResetAdd")).click();

            Thread.sleep(1800, 0);

  

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtDonorFirstName")).sendKeys(fName);

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtLastName")).sendKeys(lName);

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtAddress")).sendKeys(address);

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtContactNo")).sendKeys(contact);

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtEmailID")).sendKeys(email);

  

            WebElement bloodG = driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_ddlBloodGroup"));

            Select op = new Select(bloodG);

            op.selectByVisibleText(blood);

  

            if (gender.equalsIgnoreCase("Male")) {

                driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_rblGender_0")).click();

            } else {

                driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_rblGender_1")).click();

            }

  

            driver.findElement(By.id("cphMainContent_tcBloodDonor_tpAddDonor_txtDateOfBirth")).sendKeys(date);

  

            driver.findElement(By.name("ctl00$cphMainContent$tcBloodDonor$tpAddDonor$btnAddDonor")).click();

  

            sheet.getRow(i).createCell(8).setCellValue("Data added successfully");

            Thread.sleep(1800, 0);

  

        }

  

        FileOutputStream fos = new FileOutputStream("C:\\Users\\karan.rawat01\\Documents\\Java\\Plasma\\BloodDonors.xlsx");

        workbook.write(fos);

        workbook.close();

        fos.close();

    }

  

}