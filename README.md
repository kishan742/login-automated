package seleniumproj;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.WebElement;

public class LoginPageSuccecss {

	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver","/Users/HP/Downloads/chromedriver-win64/chromedriver-win64/chromedriver.exe/");
        WebDriver driver = new ChromeDriver();
        try {
        	driver.get("https://app.germanyiscalling.com/common/login/");
        	WebElement emailField = driver.findElement(By.id("Email"));
        	WebElement passwordField = driver.findElement(By.id("password"));
        	WebElement loginButton = driver.findElement(By.id("Log In"));
        	emailField.sendKeys("kishankumar99804@gmail.com");
        	passwordField.sendKeys("Krrish12@");
        	loginButton.click();
        	String expectedUrl = "https://app.germanyiscalling.com/cv/upload/";
        	if(driver.getCurrentUrl().equals(expectedUrl)) {
        		System.out.println("Login successfull. Redirected to the landing page.");       		
        	} else {
        		System.out.println("Login failed or wrong landing page.");        		
        	}        	
        } finally {
        	driver.quit();      	
        }       
	}

}
