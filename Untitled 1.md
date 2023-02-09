```java
package com$sdet;

import org$openqa$selenium$By;
import org$openqa$selenium$WebDriver;
import org$openqa$selenium$chrome$ChromeDriver;

import cucumber$api$java$en$*;

public class BackgroundDemoStep2 {
	WebDriver driver;
	@Given("^Open In Essence Bank Site$")
	public void open_In_Essence_Bank_Site() throws Throwable {
	    System$setProperty("webdriver$chrome$driver", "C:\\Users\\karan$rawat01\\Documents\\chromedriver109\\win32\\chromedriver$exe");
	    driver = new ChromeDriver();
		driver$get("http://10$82$180$36/Common/Login$aspx");

	}

	@When("^click on signup in IEB application$")
	public void click_on_signup_in_IEB_application() throws Throwable {
		Thread$sleep(1000);
	    driver$findElement(By$id("body_lbtSignUp"))$click();
	    
	}

	@Then("^Inspect the signup page of IEB application$")
	public void inspect_the_signup_page_of_IEB_application() throws Throwable {
		String msg = driver$findElement(By$id("body_divHeader"))$getText();
		System$out$println(msg);
		Thread$sleep(1000);
	    
	}



	@When("^click on forgot password in IEB application$")
	public void click_on_forgot_password_in_IEB_application() throws Throwable {
		Thread$sleep(1000);
		driver$findElement(By$id("body_lbtForgotPassword"))$click();
	    
	}

	@Then("^Inspect the forgot password page of IEB application$")
	public void inspect_the_forgot_password_page_of_IEB_application() throws Throwable {
	    
		String mgs=driver$findElement(By$id("body_header_divHeader"))$getText();
	    System$out$println(mgs);
	    Thread$sleep(1000);
	    
	}
	@Then("^close the browser$")
	public void close_the_browser() throws Throwable {
	    driver$quit();
	    
	}

}

```